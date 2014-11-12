# README


This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


Please feel free to use a different markup language if you do not plan to run
<tt>rake doc:app</tt>.

## Order of creation


```ruby
#generated home and about page controllers
$ rails generate controller pages home about

#updated routes.rb for root page and added about path
root "pages#home"  
get "about" => "pages#about"

#created and added partial _header.html.erb in layouts
<%= link_to "Home", root_path %>     
<%= link_to "About", about_path %>   

#added to partial render to home and about pages
<%= render 'layouts/header' %>

#added bootstrap to gemfile
gem 'bootstrap-sass'

#created bootstrap_and_customization.css.scss to /app/assets/stylesheets
@import 'bootstrap';
```



### Devise Configuration

*/Gemfile*
```ruby
gem 'devise'
$ bundle install
$ rails generate devise:install
```
*config/environments/development.rb*

```ruby
config.action_mailer.default_url_options = { :host => 'localhost:3000' }
```

*config/environments/production.rb*

```ruby
config.action_mailer.default_url_options = { :host => 'http://pinteresting-commits.herokuapp.com/' }
```

*config/routes.rb*

```ruby
root "pages#home"
```

*app/views/layouts/application.html.erb*

```ruby
<% flash.each do |name, msg| %>
     <%= content_tag(:div, msg, class: "alert alert-#{name}") %>
<% end %>
```

*config/application.rb*

```ruby
config.assets.initialize_on_precompile = false

$ rails g devise:views
```

reference for https://github.com/plataformatec/devise/wiki/How-To:-Allow-users-to-sign-in-using-their-username-or-email-address
