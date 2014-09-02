git version control 
========================================================
author: Florian D. Schneider
date: 27.08.2014
font-import: http://fonts.googleapis.com/css?family=Open+Sans:400,700,400italic&subset=latin,greek-ext,greek
font-family: 'Open Sans'
transition: none


Introduction
========================================================
type: section


why version control?
========================================================
incremental: true

- traceability of work progress
- **documentation**


why version control?
========================================================
incremental: true

- clean working directory
- non-linear development branches
- robust, structured backups
- **progressive development**

why version control?
========================================================
incremental: true

- collaborative work 
- reviewing
- easy publication
- **openness**

why version control?
========================================================

## **Quality management!**

You allready use version control!
========================================================
type: files

filename            | last updated               
------------------- | ----------
project.c           | 01.08.2014
project_v0.1.c      | 02.08.2014
project_v0.2.c      | 03.08.2014
project_v0.21.c     | 04.08.2014
project_v0.2_sonia.c| 04.08.2014

You allready use version control!
========================================================
type: files

filename            | last updated               
------------------- | ----------
project.c           | 01.08.2014
project_v0.1.c      | 02.08.2014
project_v0.2.c      | 03.08.2014
project_v0.21.c     | 04.08.2014
project_v0.2_sonia.c| 04.08.2014
project_v0.21_s.c   | 05.08.2014

You allready use version control!
========================================================
type: files

filename            | last updated               
------------------- | ----------
project.c           | 01.08.2014
project_v0.1.c      | 02.08.2014
project_v0.21.c     | 04.08.2014
project_v0.2_sonia.c| 04.08.2014
project_v0.21_s.c   | 05.08.2014
project_v0.2.c      | 07.08.2014

But:
========================================================
incremental: true

- annoying: there are so many files! 
- confusing: which is the latest version?
- not progressive: did you fix that bug in the right file? 
- requires manual back-ups



git
========================================================
- a version control system
- robust against errors
- platform independent
- geeky command line *or* user-friendly visual software

```
$ git
```

git
========================================================

filename            | last updated               
------------------- | ----------
.git                | 01.08.2014
project.c           | 01.08.2014

git
========================================================

filename            | last updated               
------------------- | ----------
.git                | 02.08.2014
project.c           | 02.08.2014

git
========================================================

filename            | last updated               
------------------- | ----------
.git                | 03.08.2014
project.c           | 03.08.2014


Basics
========================================================
type: section

How does it work?
========================================================

Terminal:

```
$ git init
```

***
![](figures/git_basics_Page_1.jpg)

How does it work?
========================================================

Terminal:

```
$ git status
# On branch master
# Changes not staged for commit
#
# Untracked files: 
# 
#      project.c
#

```

***
![](figures/git_basics_Page_2.jpg)

How does it work?
========================================================

Terminal:

```
$ git add project.c
```

***
![](figures/git_basics_Page_3.jpg)

How does it work?
========================================================

Terminal:

```
$ git commit -m "initial project.c"
```

***
![](figures/git_basics_Page_4.jpg)

How does it work?
========================================================

Terminal:

```
$ git add project.c
```

***
![](figures/git_basics_Page_5.jpg)

How does it work?
========================================================

Terminal:

```
$ git commit -m "fixed bug project.c"
```

***
![](figures/git_basics_Page_6.jpg)


How does it work?
========================================================

Terminal:

```
$ git add project.c
```

***
![](figures/git_basics_Page_7.jpg)

How does it work?
========================================================

Terminal:

```
$ git commit -m "fixed bug project.c"
$ git tag v1.0 -m "first version project.c"

```

***
![](figures/git_basics_Page_8.jpg)

How does it work?
========================================================

![](figures/commits_Page_1.png)

How does it work?
========================================================

![](figures/commits_Page_2.png)

How does it work?
========================================================

![](figures/commits_Page_3.png)


How does it work?
========================================================

![](figures/commits_Page_5.png)

How does it work?
========================================================

![](figures/commits_Page_6.png)

How does it work?
========================================================

![](figures/commits_Page_7.png)

How does it work?
========================================================

![](figures/commits_Page_8.png)

How does it work?
========================================================

![](figures/commits_Page_9.png)


Workflow
========================================================
type: section

Everyday git
========================================================
incremental: true

1. work on files
2. commit to repository
    - adding files
    
    ```
    $ git add [file]
    ```
    - commit + message
    
    ```
    $ git commit -m "edit [file]"
    ```


Once in a while git
========================================================
incremental: true

3. tagging

  ```
  $ git tag [v*.*.*] -m "[newest version]"
  ```
  
5. time travelling

  ```
  $ git checkout v1.0
  $ git checkout master
  ```

6. branching


graphical Clients
========================================================

- Windows: [GitHub for Windows](http://windows.github.com/)
- Mac: [GitHub for Mac](http://mac.github.com/)
- Linux: [git-cola](http://git-cola.github.com/)
- all: [GitEye](http://www.giteyeapp.com/), [RStudio](http://www.rstudio.com) and other IDEs have plug-ins

many more: 
http://git-scm.com/downloads/guis

Backing up & Syncing
========================================================
type: section

Working with remotes
========================================================
- for syncing your computers
- or collaboration

Working with remotes
========================================================

![](figures/remotes_Page_1.png)

Working with remotes
========================================================
![](figures/remotes_Page_2.png)

Working with remotes
========================================================
![](figures/remotes_Page_3.png)

Working with remotes
========================================================
![](figures/remotes_Page_4.png)

Working with remotes
========================================================
![](figures/remotes_Page_5.png)


GitHub
========================================================

- remote repositories
- **free** for open source projects (fully public!)
- private repositories (commercial)
- manage development (teams, tasks, milestones, wikis)

*Alternatives:* <br>[Bitbucket](https://bitbucket.org/) (free private for small teams), <br> [GitLab Cloud](https://about.gitlab.com/gitlab-com/) (unlimited free private), <br> self-hosted git server, and many more

Resources
========================================================
type: section

Resources
========================================================

https://www.atlassian.com/git

http://git-scm.com/book/

http://git-scm.com/

https://training.github.com/kit/

Exercises
========================================================
type: section


1 | working locally
========================================================
type: sub-section

1. create a git repository locally
2. generate content
3. add and commit


2 | tagging
========================================================
type: sub-section

in same repository:

1. tag
2. edit content 
3. add and commit
5. check history: `git log` 
6. checkout tag
7. return to latest version

3 | GitHub
========================================================
type: sub-section

1. create a git repository on Github.
2. clone to local Computer: <br> `git clone https://github.com/user/repo`
3. generate content
4. add and commit
5. push (requires password)
6. edit online
7. pull


4 | Collaboration
========================================================
type: sub-section

1. clone shared project
2. create a file
3. add, commit, push
4. assign an issue (i.e. a task)
5. check your tasklist
6. pull repository
7. fullfill task
8. add, commit, push
9. check out progress on tasks

etc.: Milestones, Wiki

Final Thoughts:
========================================================
type: section

Open source
========================================================

- turn private repos public!
- choose a license: GPL or MIT for code, Creative Commons for text and data

Why? 
- scientific work is of public concern
- enables re-use or inspiration
- transparency adds credibility
- scientific culture: acceptance of failure
