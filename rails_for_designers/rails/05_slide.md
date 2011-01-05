!SLIDE
# TranslationHelper #
## I18n - Internationalization ##
### Pliki z tłumaczeniami znajdują się w katalogu config/locales/ ###

!SLIDE smaller
# TranslationHelper - Przykłady ##
    @@@Html
    <%= t('main.greetings') %>
    Witaj!
    
    <%= t('main.greeting_with_name',
      :name => current_user.first_name)
    Witaj, John!