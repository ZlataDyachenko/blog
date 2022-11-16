---
title: Version control. Git.
subtitle: Introduction to the git version control system.
summary: Introduction to the git version control system.
date: 2022-10-07
math: true
image:
  placement: 2
  caption: 'Image credit: [**unknown**](https://logosource.ir/wp-content/uploads/2015/12/Git.jpg)'
---

**Version Control Systems (Version Control System, VCS)** used when several people are working on the same project. Usually, the main project tree is stored in a local or remote repository, to which access is configured for project participants. When making changes to the project content, the version control system allows you to fix them, combine changes made by different project participants, roll back to any earlier version of the project, if required.

## Theoretical information

In classical version control systems, a centralized model is used, assuming a single repository for storing files. Most version control functions are performed by a special server. The project participant (user) receives the version of files he needs before starting work through certain commands. After making changes, the user places the new version in the repository. At the same time, previous versions are not deleted from the central repository and you can return to them at any time. The server may not save the full version of the modified files, but perform a so—called delta compression - save only changes between successive versions, which reduces the amount of data stored.
Version control systems support the ability to track and resolve conflicts that may arise when several people work on a single file. You can merge (merge) changes made by different participants (automatically or manually), manually select the desired version, cancel the changes altogether or lock files for modification. Depending on the settings, the lock does not allow other users to get a working copy or prevents the OS file system from changing the working copy of the file, thus providing privileged access to only one user working with the file.
Version control systems can also provide additional, more flexible functionality. For example, they can support working with multiple versions of a single file, keeping a common history of changes up to the point of branching versions and their own change histories of each branch. In addition, information is usually available about which of the participants, when and what changes were made. Usually this kind of information is stored in the change log, access to which can be restricted. Unlike the classic ones, in distributed version control systems, a central repository is not mandatory.
Among the classic VCS, the most famous are CVS, Subversion, and among the distributed ones — Git, Bazaar, Mercurial. The principles of their work are similar, they differ mainly in the syntax of the commands used in the work.

## Git

Git is a distributed file version control system. The project was created by Linus Torvalds to manage the development of the Linux kernel. Currently supported by Junio Hamano.

The system is designed as a set of programs specially designed for their use in scripts. This makes it convenient to create specialized version control systems based on Git or user interfaces. For example, Cogito is just such an example of a frontend to Git repositories, and StGit uses Git to manage a collection of patches.

Git supports rapid separation and merging of versions, includes tools for visualization and navigation through the non-linear development history.
The Git version control system is a set of command-line programs. They can be accessed from the terminal by entering the git command with various options.
Due to the fact that Git is a distributed version control system, a backup copy of the local storage can be made by simple copying or archiving.

### Basic concepts

**Repository** — the project in which the Git system was initialized. During initialization , a hidden folder is added to the project .git. The repository stores all working files and the history of their changes.

The root folder of the project is **workspace**. It contains all the files and folders necessary for its operation.

**Storage** is the contents of a hidden folder.git. All workspace versions and service information are stored in this folder. The system automatically gives these versions a name consisting of letters and numbers. In the example above, these are be0f8e and d516600. It is not necessary to manipulate the folder .git manually. All work with the system is done by commands through special applications or the console.

**Commit** is a special command that saves a new version of the project and adds it to the repository. The saved file displays: all the changes that occurred in the workspace, the author of the changes and a short comment describing the essence of the changes. Each commit stores the complete state of the workspace, its folders and project files.

### Basic git commands

The most commonly used git commands:

– creation of the main repository tree:

{{< icon name="terminal" pack="fas" >}}
```
git init
```

– getting updates (changes) of the current tree from the central repository:

{{< icon name="terminal" pack="fas" >}}
```
git pull
```

– sending all the changes made to the local tree to the central repository:

{{< icon name="terminal" pack="fas" >}}
```
git push
```

– view the list of modified files in the current directory:

{{< icon name="terminal" pack="fas" >}}
```
git status
```

– view current changes:

{{< icon name="terminal" pack="fas" >}}
```
git diff
```

– save current changes:
– add all modified and/or created files and/or directories:

{{< icon name="terminal" pack="fas" >}}
```
git add .
```

– add specific modified and/or created files and/or directories:

{{< icon name="terminal" pack="fas" >}}
```
git add file_name
```

– delete the file and/or directory from the repository index (while the file and/or directory remains in the local directory):

{{< icon name="terminal" pack="fas" >}}
```
git rm file_name
```

– save added changes:
– save all added changes and all modified files:

{{< icon name="terminal" pack="fas" >}}
```
git commit -am 'Commit description'
```

– save the added changes with a comment through the built-in editor:

{{< icon name="terminal" pack="fas" >}}
```
git commit
```

– creating a new branch based on the current one:

{{< icon name="terminal" pack="fas" >}}
```
git checkout -b_name
```

– switching to a certain branch:

{{< icon name="terminal" pack="fas" >}}
```
git checkout branch name
```

– sending changes of a specific branch to the central repository:

{{< icon name="terminal" pack="fas" >}}
```
git push origin_name
```

– merging a branch with the current tree:

{{< icon name="terminal" pack="fas" >}}
```
git merge --no-ff_name
```

– deleting a branch:
– deleting a local branch already merged with the main tree:

{{< icon name="terminal" pack="fas" >}}
```
git branch -d branch_name
```

– forced deletion of a local branch:

{{< icon name="terminal" pack="fas" >}}
```
git branch -D branch_name
```

– deleting a branch from the central repository:

{{< icon name="terminal" pack="fas" >}}
```
git push origin :branch name
```

### Knowing these basics, you can already start working with projects.
