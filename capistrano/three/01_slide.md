!SLIDE smaller transition=fade

## crontab - whenever gem ##

    @@@Ruby
    after "deploy:symlink", "whenever:update_crontab"
    after "deploy:rollback", "whenever:update_crontab"
    
    namespace :whenever do
      desc "Update application's crontab entries using Whenever"
      task :update_crontab, :roles => whenever_roles do
        run "cd #{current_path} && whenever --update-crontab"
      end
    end
    
    # lub krócej
    require 'whenever/capistrano'

!SLIDE smaller transition=fade

## delayed_job ##

    @@@Ruby
    before "deploy:update", "delayed_job:stop"
    after "deploy:symlink", "delayed_job:start"
    after "deploy:rollback", "delayed_job:start"
    
    namespace :delayed_job do
      desc "Stop delayed_job"
      task :stop, :roles => :node do
        run "cd #{current_path} && ./script/delayed_job_ctl.rb stop"
      end
      
      desc "Start delayed_job"
      taks :start, :roles => :node do
        run "RACK_ENV=#{stage} cd #{current_path} && ./script/delayed_job_ctl.rb start"
      end
    end

!SLIDE smaller transition=fade

## RPM New Relic ##

    @@@Ruby
    # Więcej:
    # http://support.newrelic.com/faqs/docs/ruby_deployments
    require 'new_relic/recipes'
    
!SLIDE smaller transition=fade

## Hoptoad Notifier ##

    @@@Ruby
    require 'hoptoad_notifier/capistrano'

!SLIDE smaller incremental commandline transition=fade

# Przydatne #

    $ cap production deploy:upload FILES=public/images/logo.png     
    $ cap beta deploy:migrations RELEASE=branches/my_new_cool_feature
    $ cap production deploy:tail_log

!SLIDE bullets incremental transition=fade

# Dobrze, gdy ... #
  * testujesz deployment
  * masz szybkie łącze repo - serwery produkcyjne
  * nie kryjesz się z deployem
  * masz zasady deploymentu
