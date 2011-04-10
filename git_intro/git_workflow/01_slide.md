!SLIDE commandline incremental
# git - konfiguracja #

    $ git config --global user.name "Sebastian Nowak"
    $ git config --global user.email "sebastian.nowak@implix.com"
    $ git config --global color.branch auto
    $ git config --global color.diff auto
    $ git config --global color.interactive auto
    $ git config --global color.status auto
    $ git config --global core.editor "mate -w"

!SLIDE commandline incremental

# Nowe repozytorium #

    $ git init
    Initialized empty Git repository in /Users/snowak/.../git-intro-examples/.git/
    $ ls -a
    . .. .git


!SLIDE commandline

# Ignorowanie #

    $ cat .gitignore
    .idea
    .project
    .nbproject
    log/*.log

!SLIDE commandline incremental

# Stage #

    $ git status
    # On branch master
    #
    # Initial commit
    #
    # Untracked files:
    #   (use "git add <file>..." to include in what will be committed)
    #
    #       .gitignore
    nothing added to commit but untracked files present (use "git add" to track)

!SLIDE commandline incremental

# Dodawanie zmian

    $ git add .gitignore
    $ git commit -m "gitignore"
    [master (root-commit) 8f64ccd] gitignore
    1 files changed, 4 insertions(+), 0 deletions(-)
    create mode 100644 .gitignore

    $ git commit -a -m "gitignore"
    [master (root-commit) 8f64ccd] gitignore
    1 files changed, 4 insertions(+), 0 deletions(-)
    create mode 100644 .gitignore

!SLIDE commandline incremental

# Przeglądanie zmian #

     $ git log
     commit 8f64ccd811568bf7ebe9972b2961f01883b25944
     Author: Sebastian Nowak <sebastian.nowak@gmail.com>
     Date:   Thu Jul 15 14:59:30 2010 +0200

         gitignore

!SLIDE commandline incremental

    $ git log --summary --stat
    commit 8f64ccd811568bf7ebe9972b2961f01883b25944
    Author: Sebastian Nowak <sebastian.nowak@gmail.com>
    Date:   Thu Jul 15 14:59:30 2010 +0200

      gitignore

    .gitignore |    4 ++++
    1 files changed, 4 insertions(+), 0 deletions(-)
    create mode 100644 .gitignore

    $ git log --pretty=oneline
    8f64ccd811568bf7ebe9972b2961f01883b25944 gitignore
    