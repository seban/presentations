!SLIDE
# NumberHelper #
## Metody pomagające w wyświetlaniu danych liczbowych ##

!SLIDE smaller
    @@@Html
    <%= number_to_currency 1234567890.50 %>
    $1,234,567,890.50
    
    <%= number_to_currency(1234567890.506, :precision => 3) %>
    $1,234,567,890.506
    
    <%= number_to_currency(1234567890.50, :unit => "&pound;", 
      :separator => ",", :delimiter => "") %>
    &pound;1234567890,50
    
    <%= number_to_currency(1234567890.50, :unit => "&pound;", 
      :separator => ",", :delimiter => "", :format => "%n %u") %>
    1234567890,50 &pound;
    
!SLIDE smaller
    @@@Html
    <%# us locale %>
    <%= number_to_currency 12.67 %>
    12.67
    
    <%# pl locale %>
    <%= number_to_currency 12.67 %>
    12,67

!SLIDE smaller
    @@@Html
    <%= number_to_percentage 100.0 %>
    100.0%
    
    <%= number_to_percentage 1000.0, :delimiter => ".",
      :separator => ",")
    1.000,000%
