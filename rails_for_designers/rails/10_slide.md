!SLIDE
# Katalogi w projekcie Rails #

!SLIDE center
![directory](working_tree.png)

!SLIDE bullets incremental
## Nazwy ##
  * index.html.rhtml
  * index.rss.builder
  * _form.html.rhtml

!SLIDE smaller
## Layout ##
    @@@Html
    <html>
      <head>
        <title>Super site!</title>
        <%= stylesheet_link_tag :all %>
        <%= javascript_include_tag :defaults %>
        <%= csrf_meta_tag %>
      </head>
      <body>
        <div class="content main">
          <%= yield %>
        </div>
      </body>
    </html>

!SLIDE smaller
## Partiale ##
    @@@Html
    New & edit user
    <%= render "form" %>
    <%= render :partial => "form" %>
    app/views/users/new.html.rhtml
    app/views/users/_form.html.rhtml

    <% form_for @user do %>
    <% end %>

!SLIDE smaller
## Paritale - locals ##
    @@@Html
    <%= render "form", :locals => { :user => @user, 
      :action_type => "Edit" } %>
    
    <% form_for user do %>
      <p>Please #{ action_type } user</p>
    <% end %>

!SLIDE smaller
## Partiale - object ##
    @@@Html
    <%= render :partial => "user", :object => @user %>
    <%= render @user %>
      
    # partial _user.html.rhtml
    <p>
      User login: <%= user.login %>
    </p>

!SLIDE smaller
## Partiale - collection ##
    @@@Html
    <%= render :parital => "user", :collection => @users %>
    <%= render @users %>
    
    # partial _user.html.rhtml
    <p>
      User login: <%= user.login %>
    </p>
