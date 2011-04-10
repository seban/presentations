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

!SLIDE smbullets incremental
# Branch #
## Koncepcja feature brancha ##

  * łatwo stworzyć nowe odgałęzienie
  * łatwo przechodzić między gałęziami
  * łatwo zarządzać gałęziami
  * łatwo zrobić merga
  * łatwo przeglądać zmiany w różnych gałęziach
  * łatwo ...
  * trudno tego nie polubić

!SLIDE commandline incremental
# Nowy branch #

    $ git checkout -b my_new_branch
    Switched to a new branch 'my_new_branch'
    
    $ git branch my_2nd_branch
    
    $ git branch my_3rd_branch eac1fd4
    
    $ git branch --track my_4th_branch origin/my_4th_branch

!SLIDE commandline incremental
# Pokaż mi wszystkie #

    $ git branch -av
    * master              eae059d Dodanie wsparcia dla logowania operacji
    my_2nd_branch         eae059d Dodanie wsparcia dla logowania operacji
    my_3rd_branch         eac1fd4 Initialize project
    my_4th_branch         [ahead 3] 74265d7 Dokumentacja
    remotes/origin/master eae059d Dodanie wsparcia dla logowania operacji
    remotes/origin/my_4th eae059d Dodanie wsparcia dla logowania operacji

!SLIDE commandline
# Przeskocz z gałęzi na gałąź #

    $ git checkout my_2nd_branch

!SLIDE center
# Scalanie gałęzi #
## sytuacja wyjściowa ##
![img/18333fig0327-tn.png](img/18333fig0327-tn.png)

!SLIDE center commandline
# Scalanie gałęzi - merge #
## w wyniku merge może powstać kolejny commit ##

![img/18333fig0328-tn.png](img/18333fig0328-tn.png)

    $ git merge my_new_branch

!SLIDE center commandline
# Rebase & merge #

![img/18333fig0329-tn.png](img/18333fig0329-tn.png)
    
    $ git rebase master
    $ git checkout master
    $ git merge my_new_branch

!SLIDE center
# Czym gałęzie się różnią #

    $ git diff master my_new_branch
    
    $ git diff master my_new_branch --stat
    
    $ git log master..my_new_branch --oneline

!SLIDE center
# Tagi #
![img/tags.jpg](img/tags.jpg)

!SLIDE commandline incremental
# git tag #

    $ git tag
    $ git tag -l 'v1.1.*'
    $ git tag 'v1.5'
    $ git tag -a v1.4.4 -m 'Wydanie nowej wersji'
    $ git push origin tag_name
    $ git push origin --tags

!SLIDE center
## git-svn ##
![img/cosielubi.jpg](img/cosielubi.jpg)
