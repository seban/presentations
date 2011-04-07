!SLIDE center
# git remote #

## Służy do wymiany - współdzielenia kodu z innymi ##

!SLIDE commandline

    $ git remote
    # pusto
    $ git remote add origin ssh://snowak@web-b-test.v.l/home/snowak/git/git-intro.git
    $ git remote -v
    origin  ssh://snowak@web-b-test.v.l/home/snowak/git/git-intro.git (fetch)
    origin  ssh://snowak@web-b-test.v.l/home/snowak/git/git-intro.git (push)
    
!SLIDE commandline incremental

    $ git push origin master
    Counting objects: 11, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (7/7), done.
    Writing objects: 100% (11/11), 917 bytes, done.
    Total 11 (delta 1), reused 0 (delta 0)
    To ssh://snowak@web-b-test.v.l/home/snowak/git/git-intro.git
     * [new branch]      master -> master
     
!SLIDE commandline incremental

## Pobieranie zewnętrznych zmian - nowe repo

### svn checkout
    
    $ git clone ssh://mkuzel@web-b-test.v.l/home/snowak/git/git-intro.git
    
    * inicjalizuje nowe lokalne repozytorium
    * tworzy 'domyślny' remote - origin
    
!SLIDE commandline incremental

## Pobieranie zewnętrznych zmian - aktualizacja

### svn up

    $ git fetch origin
    
    * uaktualnia remote, wszystkie branche i tagi
    * nie zmienia lokalnych gałęzi - konieczny merge
    
    $ git pull origin master
    
    * uaktualnia remote, tylko jeden branch
    * wykonywany jest merge z lokalnym branchem

!SLIDE center
## git-svn ##
![img/cosielubi.jpg](img/cosielubi.jpg)
