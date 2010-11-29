!SLIDE smbullets incremental transition=fade

# Capistrano #

* ujednolicony interfejs
* automatyzacja
* wiele strategii
* wiele środowisk
* wiele serwerów jednocześnie
* wiele ról serwerów

!SLIDE commandline incremental transition=fade

# Interfejs #

    $ cap deploy:check
    $ cap deploy:setup
    $ cap deploy:cold
    $ cap deploy:migrations
    $ cap deploy
    
!SLIDE smaller transition=fade
.notes Kod deploy

# Automatyzacja #

    namespace :deploy do
      task :default do
        update
        restart
      end
      
      task :update do
        transaction do
          update_code
          symlink
        end
      end
    end
    
!SLIDE commandline incremental transition=fade
    
# Środowiska - stage
    
    $ cap beta deploy
    $ cap production deploy
