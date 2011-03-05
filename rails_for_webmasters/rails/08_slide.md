!SLIDE center
## HTML5 & Rails ##
![HTML 5](we-can-do-html5.jpg)

!SLIDE smaller
## HTML5 Inputs ##
    @@@Html
    <%= email_field :user, :email %>
    <input type="email" name="user[email]" id="user_email" />
    
    <%= number_field :user, :age, :min => 18 %>
    <input type="number" name="user[age]" id="user_age" min="18" />
    
    <%= range_field :user, :salary, :min => 3_000, :max => 10_000 %>
    <input type="range" name="user[salary]" id="user_salary"
      min="3000" max="10000" />

!SLIDE smaller
## HTML5 Inputs ##
    @@@Html
    <%= search_field :query, :login %>
    <input type="search" name="query[login]" id="query_login" />
    
    <%= phone_field :user, :phone %>
    <input type="tel" name="user[phone]" id="user_phone" />
    
    <%= url_field :user, :url %>
    <input type="url" name="user[url]" id="user_url" />

!SLIDE smaller
## HTML5 Custom attributes ##
    @@@Html
    <%= textarea_tag :user, :signature,
      "data-counter" => "span#signature_counter" %>

    <%= link_to "Delete", user_path(@user), :method => :delete
      :confirm => "Are you sure?" %>
    <a href="/users/1024" data-method="delete"
      data-confirm="Are you sure?">Delete</a>

!SLIDE smaller
    @@@Html
    <%= video_tag "promo">
    <video src="/videos/trailer" />
    
    video_tag("trailer.m4v", :size => "16x10",
      :poster => "screenshot.png")
    <video src="/videos/trailer.m4v" width="16" height="10"
      poster="/images/screenshot.png" />
