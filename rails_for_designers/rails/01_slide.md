!SLIDE center bullets incremental
# Rails #
## MVC framework for web applications ##

  * Model
  * View
  * Controller

!SLIDE smbullets center incremental
## Rails views presentation layer ##
## Popular solutions ##
  
  * ERb - Embedded Ruby
  * HAML
  
!SLIDE
## ERb ##

    @@@Ruby
    <b>Dziś jest:</b> <%= Date.today.to_s %>
    <b>Dziś jest:</b> 2011-01-06

!SLIDE
    @@@Ruby                           
    <ul>
    <% [1,2,3,4,5].each do |number| %>
      <li>Numerek to: <%= number %></li>
    <% end %>
    </ul>
    <ul>
      <li>Numerek to: 1</li>
      <li>Numerek to: 2</li>
      <li>Numerek to: 3</li>
      <li>Numerek to: 4</li>
      <li>Numerek to: 5</li>
    </ul>

!SLIDE small
    @@@Ruby
    <p>
      <% if logged_in? %>
        Jesteś zalogowany jako: <%= current_user.login %>
      <% else %>
        <%= link_to "Zaloguj sie", signup_url %>
      <% end %>
    </p>
    <p>Jesteś zalogowany jako: my_login</p>
    <p><a href="/singup">Zaloguj się</a></p>