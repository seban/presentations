!SLIDE
# UrlHelper #
### Metody pomagające budować linki ###

!SLIDE smaller
## UrlHelper - Przykłady ##
    @@@Html
    <%= button_to "Delete", { :action => "delete",
      :id => @image.id }, :confirm => "Are you sure?",
      :method => "delete" %>
    <form class="button_to" action="/images/1024" method="post">
      <div> 
        <input type="hidden" name="_method" value => "delete" />
        <input type="submit" value="Delete"
          data-confirm="Are you sure?" />
      </div>
    </form>

!SLIDE smaller
    @@@Html
    <%= link_to "Google it!", 'http://google.com' %>
    <a href="http://google.com">Google it!</a>

    <%= link_to "Users", :controller => "users",
      :action => "index" %>
    <a href="/users/">Users</a>

    <%= link_to "Users", users_path, :class => "big_link" %>
    <a href="/users" class="big_link">Users</a>

    <%= link_to "User", :controller => "users",
      :action => "show", :id => @user.id %>
    <a href="/users/1024">User</a>

    <%= link_to "User", user_path(@user) %>
    <a href="/users/1024">User</a>

!SLIDE smaller
    @@@Html
    <% link_to "User profile", user_path(@user) do %>
      <%= image_tag @user.avatar_url %>
    <% end %>
    <a href="/users/1024">
      <img. src="/images/avatars/1024/avatar.png" />
    </a>