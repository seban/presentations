!SLIDE bullets
# AssetHelper #
## Metody pomagające w korzystaniu w assetów: ##
  * pliki CSS
  * pliki JavaScript
  * obrazki
  
!SLIDE smaller
## AssetHelper - Przykłady ##
    @@@Html
    <%= image_tag('rails.png') %>
    <img src="/images/rails.png" />
    
    <%= image_tag('rails.png', :class => "images logo")
    <img src="/images/rails.png" class="images logo" />
    
    <%= image_tag('rails.png', :alt => "To jest logo Rails")
    <img src="/images/rails.png" alt="To jest logo Rails" />
    
    <%= image_tag('content/logo.png') %>
    <img src="/images/content/logo.png" />

!SLIDE smaller
# AssetHelper - Przykłady #
    @@@Html
    <%= javascript_include_tag 'jsonp' %>
    <script type="text/javascript" src="javascripts/jsonp.js"></script>
    
    <%= javascript_include_tag 'jsonp', 'jquery', 'application' %>
    <script type="text/javascript" src="javascripts/jsonp.js"></script>
    <script type="text/javascript" src="javascripts/jquery.js"></script>
    <script type="text/javascript" src="javascripts/application"></script>

!SLIDE smaller
# AssetHelper - Przykłady #
    @@@Html
    <%= stylesheet_link_tag 'forms' %>
    <link href="/stylesheets/form.css" media="screen" 
      rel="stylesheet" type="text/css" />
    
    <%= stylesheet_link_tag "shop", "cart", "checkout",
      :cache => "payment" %>
    <link href="/stylesheets/payment.css"  media="screen"
      rel="stylesheet" type="text/css" />
      
    <%= styleshet_link_tag :all, :cache => true,
      :recursive => true %>
    <link href="/stylesheets/all.css"  media="screen"
      rel="stylesheet" type="text/css" />
    
    
