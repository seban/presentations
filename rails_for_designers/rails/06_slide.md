!SLIDE
# FormHelper #
## Budowanie formularzy ##

!SLIDE smaller
## FormHelper - Przykład ##
    @@@Html
    <% form_for :person, @person, :url => { :action => "create" } do |f| %>
      <%= f.text_field :first_name %>
      <%= f.text_field :last_name %>
      <%= submit_tag 'Create' %>
    <% end %>
    
    <form action="/persons/create" method="post">
      <input id="person_first_name" name="person[first_name]"
        size="30" type="text" />
      <input id="person_last_name" name="person[last_name]" 
        size="30" type="text" />
      <input name="commit" type="submit" value="Create" />
    </form>
    
!SLIDE smaller
    @@@Html
    <%= check_box(:user, :tos_approved, ) %>
    <input type="checkbox" name="user[tos_approved]" value="1"/>
    <input type="hidden" name="user[tos_approved]" value="0" />
    
    <%= check_box(:user, :tos_approved, :id => "tos_approved") %>
    <input type="checkbox" name="user[tos_approved]"
      id="tos_approved" value="1"/>
    <input type="hidden" name="user[tos_approved]" value="0" />
    
    <%= check_box(:user, :tos_approved, :class => "input check") %>
    <input type="checkbox" name="user[tos_approved]"
      class="input check" value="1"/>
    <input type="hidden" name="user[tos_approved]" value="0" />

    <%= check_box(:user, :tos_approved, {}, "Accepted", "Declined")
    <input type="checkbox" name="user[tos_approved]" value="Accepted" />
    <input type="hidden" name="user[tos_accepted]" value="Declined" />

!SLIDE smaller
    @@@Html
    <%= file_field :user, :avatar %>
    <input type="file" name="user[avatar]" id="user_avatar">

    <%= file_field :user, :avatar, :class => "uploader" %>
    <input type="file" name="user[avatar]" id="user_avatar"
      class="uploader" />

!SLIDE small
    @@@Html
    <%= hidden_field :user, :hide_me , :value => 1%>
    <input type="hidden" name="user[hide_me]" value="1" />

!SLIDE smaller
    @@@Html
    <%= password_field :user, :password %>
    <input type="password" name="user[password]"
      id="user_password" />

    <%= password_field :user, :password, :size => 20,
      :class => "pass_field" %>
    <input type="password" name="user[password]"
      id="user_password" size="20" class="pass_field" />

!SLIDE smaller
    @@@Html
    <%= textarea_tag :user, :signature %>
    <textarea cols="20" rows="20" id="user_signature" name="user[signature]">
      <%= @user.signature %>
    </textarea>

    <%= textarea_tag :user, :signature, :rows => 10,
      :cols => 7, :class => "text" %>
      
    <textarea cols="7" rows="10" class="text" id="user_signature" name="user[signature]">
      <%= @user.signature %>
    </textarea>

!SLIDE small
    @@@Html
    <%= text_field :user, :name %>
    <input type="text" id="user_name" name="user[name]" />

    <%= text_field :user, :name, :class => "text" %>
    <input type="test" id="user_name" name="user[name]"
      class="text" />

!SLIDE small
    @@@Html
    <%= label :user, :login %>
    <label for="user_login">Login</label>

    <%= label :user, :login, :class => "label" %>
    <label for="user_login" class="label">Login</label>