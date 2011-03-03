!SLIDE center
![octocat](rails_logo.jpg)

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
    
!SLIDE smaller
    @@@Html
    <table>
    <% @payouts.each do |payout| %>
      <tr class="<%= cycle("odd", "even") %>">
        <td><%= payout.amount %></td>
        <td><%= payout.created_at.to_s(:only_date) %></td>
        <td><%= link_to "Show", payout_path(payout) %>
      </tr>
    <% end %>
    </table>
    
!SLIDE smaller
    @@@Html
    <table>
      <tr class="odd">
        <td>45.89</td>
        <td>2011-02-15</td>
        <td><a href="/payouts/2">Show</a>
      </tr>
      <tr class="even">
        <td>205.14</td>
        <td>2011-01-15</td>
        <td><a href="/payouts/1">Show</a>
      </tr>
    </table>
    
!SLIDE smaller
# HAML #
    %table
      - @payouts.each do |payout|
        %tr{ :class => cycle("odd", "even") }
          %td= payout.amount
          %td= payout.created_at.to_s(:only_date)
          %td= link_to "Show", payout_path(payout)

!SLIDE small
    @@@Ruby
    <p>
      <% if logged_in? %>
        Jesteś zalogowany jako: <%= current_user.login %>
      <% else %>
        <%= link_to "Zaloguj sie", signup_path %>
      <% end %>
    </p>
    <p>Jesteś zalogowany jako: my_login</p>
    <p><a href="/singup">Zaloguj się</a></p>
