git version control 
========================================================
author: Florian D. Schneider
date: 27.08.2014
font-import: http://fonts.googleapis.com/css?family=Open+Sans:400,700,400italic&subset=latin,greek-ext,greek
font-family: 'Open Sans'
transition: none


We are going to learn today:
========================================================
incremental: true

1. version control is useful, really!
2. **git** is a simple version control system  
3. how to get started using git for our personal work


Introduction
========================================================
type: section


why version control?
========================================================
incremental: true

- know what you did and when you did it! 
- documentation & development history 
- do robust, structured backups!

## reproducibility

why version control?
========================================================
incremental: true

- don't go back and forth!
- manage your non-linear development! 
- write re-usable code!

## progressive development

why version control?
========================================================
incremental: true

- collaborate on code and text! 
- enable structured code review 
- publish your code 

## openness


========================================================
incremental: true

## reproducibility
## progressive development
## openness
## = 
## Quality management!




But: hey! 
========================================================
type: section

You already use version control! 
========================================================

### *(kind of)*


You already use version control! 
========================================================
type: files

filename            | last updated               
------------------- | ----------
project.c           | 01.08.2014


You already use version control! 
========================================================
type: files

filename            | last updated               
------------------- | ----------
project.c           | 01.08.2014
project_v0.1.c      | 02.08.2014


You already use version control! 
========================================================
type: files

filename            | last updated               
------------------- | ----------
project.c           | 01.08.2014
project_v0.1.c      | 02.08.2014
project_v0.2.c      | 03.08.2014
project_v0.21.c     | 04.08.2014
project_v0.2_sonia.c| 04.08.2014

You already use version control!
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

You already use version control!
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

it's annoying!
========================================================
- There are so many files! 

it's confusing!
========================================================
- Which one was the latest version?
- OMG, I can show that to no one!

it's not progressive or reproducible
========================================================
- Did I fix that bug in the right file now?  
- What version of that function is this?  
- Which version of the code was used to produce this result? 

it's not helping at all
========================================================
incremental:true

- I still need to do manual back-ups!  
- I still cannot reproduce what I did!
- Others cannot reproduce what I did!

git:  a version control "system"
========================================================
type: section

git
========================================================
incremental: true

- it's a version control "system" 
- robust against errors
- transparent structure
- works for code
- works for databases
- works for writing, too!
- geeky command line 

```
$ git push origin master
```
- *or* user-friendly graphical software


========================================================

![](figures/github_for_windows.png)


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

Concepts
========================================================

*Classic filesystems:*

- directories:  
  <img src = "figures/folder.svg" style = "height: 1.4em; margin-bottom: 0; "/>
- files:  
  <img src = "figures/file.svg" style = "height: 2em; margin-bottom: 0; "/>
  
***

*git:*
- repository:   
  - commits:  
  <img src = "figures/commit.svg" style = "height: 2em; margin-bottom: 0; "/>
  - pointers:  
  <img src = "figures/pointer.svg" style = "height: 1em; margin-bottom: 0;"/>
  - working directory:  
    <img src = "figures/file.svg" style = "height: 2em; margin-bottom: 0; "/>  & <img src = "figures/folder.svg" style = "height: 1.4em; margin-bottom: 0; "/>


<!-- here: replace series about commits with a basic network graph. -->

\begin{tchncl}
=======================================================
type: section

What is a repository?
========================================================
incremental: true

<img src="figures/folder.svg" style = "height: 6em;">  
{demo}  

- it's a directory
- it contains meta-data  
- it contains *'commits'*  


What are commits?
========================================================
incremental: true

<img src="figures/commit.svg" style = "height: 5em;">  

- instructions to change one file or multiple files
- instructions to remove or add files

What are commits?
========================================================
incremental: true

<img src="figures/commit.svg" style = "height: 5em;">  

- each commit has a unique name: a **hash-tag** 
  `#5b26a8379e0f1ea6dd87916d738a49d118361676`
- meta info: 
  - commiter name and e-mail, time and date of commit
  - a **commit message**
  - a reference to it's **parent** (pointer)

what are pointers? 
========================================================
incremental: true


<img src="figures/pointer.svg" style = "height: 2.5em; margin: 1.5em 0;">  

- **a reference to a commit** 
- they connect commits *upstream*

what are pointers? 
========================================================
incremental: true

<img src="figures/pointer.svg" style = "height: 2.5em; margin: 1.5em 0;">  

Types of pointers:  
- 'tags' <img src="figures/tag1-0.svg" style = "height: 1em; margin: 0;">  <img src="figures/tag1-2.svg" style = "height: 1em; margin: 0;"> 
- 'branches' <img src="figures/branch-master.svg" style = "height: 1em; margin: 0;"> <img src="figures/branch-test.svg" style = "height: 1em; margin: 0;"> 
- **the 'HEAD' of your repository** <img src="figures/HEAD.svg" style = "height: 1em; margin: 0;">   



What is a repository, really? 
========================================================
incremental: true

- a repository consists of commits
- each commit contains instructions for edits
- each commit has a pointer to it's parent
- additional pointers as references


What is a repository, really? 
========================================================

- a repository consists of commits
- each commit contains instructions for edits
- each commit has a pointer to it's parent
- additional pointers as references

<img src="figures/commit_alone.svg" style = "height: 1em;"><img src="figures/commit.svg" style = "height: 1em;"><img src="figures/branch-master.svg" style = "height: 0.8em;">  <img src="figures/HEAD.svg" style = "height: 0.8em;"> <img src="figures/folder.svg" style = "height: 1em;">

What is a repository, really? 
========================================================

- a repository consists of commits
- each commit contains instructions for edits
- each commit has a pointer to it's parent
- additional pointers as references

<img src="figures/commit_alone.svg" style = "height: 1em;"><img src="figures/commit.svg" style = "height: 1em;"><img src="figures/commit.svg" style = "height: 1em;"><img src="figures/branch-master.svg" style = "height: 0.8em;">  <img src="figures/HEAD.svg" style = "height: 0.8em;">  <img src="figures/folder.svg" style = "height: 1em;">

What is a repository, really? 
========================================================

- a repository consists of commits
- each commit contains instructions for edits
- each commit has a pointer to it's parent
- additional pointers as references

<img src="figures/commit_alone.svg" style = "height: 1em;"><img src="figures/commit.svg" style = "height: 1em;"><img src="figures/commit.svg" style = "height: 1em;"><img src="figures/commit.svg" style = "height: 1em;"><img src="figures/branch-master.svg" style = "height: 0.8em;">  <img src="figures/HEAD.svg" style = "height: 0.8em;"> <img src="figures/folder.svg" style = "height: 1em;">

What is a repository, really? 
========================================================

<img src="figures/tree-full.svg" style = "height:450px;">

the working directory
========================================================

<img src="figures/tree-master.svg" style = "height:450px;">

**the working directory is  
showing the accumulated commits at 'HEAD'**



the working directory
========================================================

<img src="figures/tree-feature.svg" style = "height:450px;">

And this is how 'time travelling' works:  
you can move HEAD to **branches**


the working directory
========================================================

<img src="figures/tree-f1.svg" style = "height:450px;">

And this is how 'time travelling' works:  
you can move HEAD to **tags**


the working directory
========================================================

<img src="figures/tree-master.svg" style = "height:450px;">

And this is how 'time travelling' works:  
you can move HEAD back to **'master' branch**
  
the working directory
========================================================

<img src="figures/tree-hash.svg" style = "height:450px;">

And this is how 'time travelling' works:  
you can move HEAD to *any* commit (per hash-tag)

  
\end{tchncl}
=======================================================
type: section


Questions?
========================================================
type: section


A word on filetypes
=======================================================

### binary files 
- .docx, .ppt, .pdf, .jpg, .xls
- 'closed' filetypes
- edits can't be tracked
- **not well suited for VC**

***

### pure text files
- .r, .cpp, .txt, .tex, .md, .csv
- 'open' filetypes
- **perfect for VC**


How does it work?
========================================================

What you need to learn:
- git startet **(Exercise 1)**
  - how to create a repository
  - how to build a commit 
- time travelling  **(Exercise 2)**
  - how to set tags
  - how to move your HEAD
- how to back-up or sync  **(Exercise 3)**
  - configure *remotes*
  - push and pull


1 | git started
========================================================
type: sub-section

1. create a git repository
2. generate content
3. do commits

Create a repository
========================================================

open a terminal

```
$
```

Create a repository
========================================================

Create a new folder. 

```
$ mkdir test
$ cd test
$
```

Create a repository
========================================================

Initialise a git repository.

```
$ mkdir test
$ cd test
$ git init
Initialized empty Git repository ...
$
```

Generate initial content
========================================================

- create a *text* file (*e.g.*, test.txt)
- create/copy a code file
- ... 

Generate initial content
========================================================

check the status!

```
$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        test.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Commit
========================================================

This is a two step process:

1. staging files for next commit  

  ```
  $ git add test.txt
  ```
  - chose files or edits for the next commit
  - wrap 'meaningful' commits

2. commit to repository 
    
```
$ git commit -m "edit test.txt: fix #23"
```
  - commit message is obligatory: `-m "..."` 

Commit
========================================================

check status again!

```
$ git status
On branch master
nothing to commit, working directory clean
```

Commit
========================================================

have a look at your repository tree!

```
$ git log
commit a9b0697265feb5013eced9c1befb9a10a94a66cb
Author: Florian Schneider <florian.schneider@univ-montp2.fr>
Date:   Fri Nov 21 16:30:53 2014 +0100

    edit test.txt
    
```

1 | git started
========================================================
type: sub-section

1. create a git repository
2. edit content
3. do commits

(repeat 2 & 3 a couple of times! use `git status` and `git log`!)


2 | tagging
========================================================
type: sub-section

in same repository:

1. add a 'tag'
2. edit content 
3. add and commit
5. check history: `git log` 
6. checkout tag
7. return to latest version


Add a tag
========================================================

Terminal:

```
$ git tag -a v1.0 -m "first version of project"
$
```


Commit
========================================================

continue work: 
 - edit
 - add and commit 


Time traveling
========================================================

```
$ git tag
v1.0
$
```


Time traveling
========================================================

```
$ git tag
v1.0
$ git checkout v1.0
$
```

look at your files!



Time traveling
========================================================

```
$ git tag
v1.0
$ git checkout v1.0
$ git checkout master
$
```

look at your files!

1 & 2 | completed
========================================================
type: sub-section

what you learned:

- create a new repository
- add and commit
- check `log` and `status`
- add 'tags' as references
- check-out different commits


Congrats!
========================================================
type: section

graphical Clients
========================================================

- Windows: [GitHub for Windows](http://windows.github.com/)
- Mac: [GitHub for Mac](http://mac.github.com/)
- Linux: [git-cola](http://git-cola.github.com/)
- all: [smartGitHg](http://www.syntevo.com/smartgit/), [GitEye](http://www.giteyeapp.com/), [RStudio](http://www.rstudio.com) and other IDEs have plug-ins

and many more: [http://git-scm.com/downloads/guis](http://git-scm.com/downloads/guis)


Remotes
========================================================
type: section

Why working with remotes?
========================================================
- back-up
- syncing your computers
- collaboration


Remotes
========================================================

![](figures/remotes_Page_1.png)

Remotes
========================================================
![](figures/remotes_Page_2.png)

Remotes
========================================================
![](figures/remotes_Page_3.png)

Remotes
========================================================
![](figures/remotes_Page_4.png)

Remotes
========================================================
![](figures/remotes_Page_5.png)


Clones
========================================================


- you can **clone** existing repositories from remotes

```
git clone https://github.com/cascade-wp6/git_intro.git
```

- your local repository will refer to the *original* repository as **origin**
- you can **pull** from and **push** to origin:

```
git pull origin master
git push origin master
```

more info: [http://git-scm.com/book](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)


GitLab at UM2
========================================================

[https://gitlab.info-ufr.univ-montp2.fr/](https://gitlab.info-ufr.univ-montp2.fr/)

![](figures/gitlab.png)

GitLab at UM2
========================================================

[https://gitlab.info-ufr.univ-montp2.fr/](https://gitlab.info-ufr.univ-montp2.fr/)

- no third party, non-commercial
- hosting of remote repositories
- free private or public projects 
- collaborate (teams, tasks)

GitHub
========================================================

[https://github.com/](https://github.com/)

![](figures/github.png)

GitHub
========================================================

[https://github.com/](https://github.com/)

- hosting of remote repositories
- free for open source projects (fully public!)
- private repositories (commercial)
- collaborate (issues, teams, access control)
- manage projects (milestones, wikis)

Alternatives 
========================================================

[Bitbucket](https://bitbucket.org/) (free private for small teams)  

[GitLab Cloud](https://about.gitlab.com/gitlab-com/) (unlimited free private)

self-hosted git server, and many more


3 | Remotes
========================================================
type: sub-section

1. create a git repository on Gitlab or Github.
2. clone to local Computer: <br> `git clone https://github.com/user/repo`
3. generate content
4. add and commit
5. push (requires password)
6. edit online
7. pull



What we learned today:
========================================================
incremental: true

1. version control is useful, really!
2. **git** is a simple version control system  
3. how to get started using git for our personal work

<br>

### we might learn later

- how to fix version conflicts
- how to develop workflows
- how git can be used to collaborate


Resources
========================================================
type: section

Resources
========================================================

https://www.atlassian.com/git/

http://git-scm.com/book/

http://git-scm.com/

https://training.github.com/kit/


Final Thoughts:
========================================================
type: section

Open source
========================================================
type: sub-section

- turn private repos public!
- [choose a license](http://choosealicense.com/): GPL or MIT for code, Creative Commons for text and data

Why? 
- scientific work is public property
- speeding up science: enable re-use & inspiration
- adds credibility and originality
- reproducibility 