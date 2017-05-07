---
layout: post
title:  "Routing: The Rails Matchmaker"
date:   2017-01-07 11:50:27 -0400
categories: Jen's bloggy
---
Routing connects your HTTP requests such as get, post, patch/put and delete to a path that then maps back to a controller and it’s actions, which are the methods defined within your controller and then renders it’s corresponding view page. Routing also helps generate URLs and paths using helpers. You can declare your routes in the folder/file config/routes and then run the command line **$rake routes** in your terminal to see all your routes. This will list your HTTP requests, the URL and then the controller action and is helpful in keeping track of the routes that you’ve declared.

When the HTTP request is sent from your browser, it goes to your routes before it knows which controller and action it should perform. Within your controller methods, it renders or redirects to the corresponding view page that you want your users to see. The view page contains your HTML code, which generates what you’ll see on the page.

Rails also grabs all the information pertaining to your object and packages it in a hash called params. In your controller edit or new method, you can use your object’s name as your key to access the information about your object with **params[:object]**. This matches back to how params is structured in the form. Rail form helpers also formats params for us because it’s nice. However, you can do it manually. Then in your views you can use your model in your form submissions to create or edit objects:

{% highlight ruby %}
#new.html.erb & edit.html.erb
<%= form_for @post do |f| %>
 <%= f.label :attribute %>
 <%= f.text_field :attribute %>
<% end %>
Corresponds to params[:post] within your controller
{% endhighlight %}

Instead of declaring routes separately, there is also a default route option called resources. The resources route creates the below 7 *REST*-ful routes for you:

**config/routes.rb**
**get "/posts" => "posts#index"** <br>
Shows all of the posts & is a part of the CRUD which reads your all of the posts & renders your index.html.erb view page

**get "/posts/:id" => "posts#show"** <br>
Grabs an individual post using params[:id] & is also part of the CRUD which reads an individual post & renders your show.html.erb view page

**get "/posts/new" => "posts#new"** <br>
Allows you to create a new post by *getting* and rendering the form_for in your new.html.erb view page

**post "/posts" => "posts#create"** <br>
*Posts* the new post based on the post params from the new form_for & saves it to the database

**get "/posts/:id/edit" => "posts#edit"** <br>
Allows you to *edit* a specific post & renders the form_for in your edit.html.erb view page

**put/patch "/posts/:id" => "posts#update"** <br>
*Updates* a specific post's attributes, part of CRUD

**delete "/posts/:id" => "posts#destroy"** <br>
*Deletes* a specific post & part of CRUD

You can declare a resources route in your -
{% highlight ruby %}
#config/routes.rb
resources :posts
{% endhighlight %}

Rails knows to map all the common RESTful HTTP requests to your CRUD controller actions: **index, show, new, edit, create, update and destroy** within a neat single line of code. If you don’t want to declare all of the RESTful routes, you can only show specific page(s) or exclude specific page(s):

{% highlight ruby %}
#config/routes.rb
resources :posts, :only => [:index, :show]
resources :users, :except => [:index]
{% endhighlight %}

You can also tack on and declare multiple resources within the same line with -

{% highlight ruby %}
resources :posts, :users, :blogs
{% endhighlight %}

To learn more about [routing](http://guides.rubyonrails.org/routing.html).
