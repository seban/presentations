!SLIDE
# Workflow #
## przykładowy workflow z git #

!SLIDE small commanline
# Nowy feature branch #

    $ git checkout -b support_for_operation_logging
    Switched to a new branch 'support_for_operation_logging'

!SLIDE smaller commandline
# Implementacja, test, dokumentacja #
## Done, done, done ##

    $ git add lib/logger.rb lib/operation.rb test/operation_test.rb
    $ git commit -m 'Dodanie wsparcia dla logowania operacji'
    [support_for_operation_logging eae059d] Dodanie wsparcia dla logowania operacji
    1 files changed, 1 insertions(+), 0 deletions(-)
    create mode 100644 lib/logger.rb
    create mode 100644 lib/operation.rb
    create mode 100644 test/operation.rb

!SLIDE commandline
# Ujednolicenie drzewa #

    $ git checkout master
    $ git pull
    $ git checkout support_for_operation_logging
    $ git rebase master

!SLIDE commandline
# Merge brancha i push #
## Podzielmy się naszą pracą ##

    $ git checkout master
    $ git merge support_for_operation_logging
    $ git push