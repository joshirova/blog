---
title: Version control. Git. 
subtitle: Welcome 👋 What is a "version control system" and why is it important? A version control system is a system that records changes to a file or set of files over time and allows you to revert to a specific version later. For file versioning, this book will use software source code as an example, although you can actually use versioning for just about any type of file.

# Summary for listings and search engines
summary: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Link this post with a project
projects: []

# Date published
date: '2023-03-18T00:00:00Z'

# Date updated
lastmod: '2023-03-18T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
  focal_point: ''
  placement: 2
  preview_only: false

authors:
  - admin

tags:
  - Git

categories:
  - post 2
---

```python
import libr
print('hello')
```

## Overview

1. About the version control system

If you're a graphic or web designer and want to save every version of an image or layout (most likely you will), a version control system (hereinafter referred to as VCS) is just what you need. It allows you to return files to the state they were before the changes, return the project to its original state, see the changes, see who last changed something and caused the problem, who set the task and when, and much more. Using VCS also generally means that if you break something or lose files, you can easily fix it. In addition to everything, you will get all this without any additional effort.

2. Local version control systems

Many people use copying files into a separate directory as a version control method (perhaps even a timestamped directory, if they're smart enough). This approach is very common due to its simplicity, but it is incredibly error prone. It's easy to forget which directory you're in and accidentally change the wrong file or copy the wrong files.

To solve this problem, programmers long ago developed local VCSs with a simple database that keeps a record of all changes to files, thus providing revision control.

![Figure 1. Local version control](local.png)
Figure 1. Local version control.

One popular VCS was the RCS system, which is still distributed with many computers today. RCS stores sets of patches (differences between files) on disk in a special format, using which it can recreate the state of each file at a given point in time.

3. Centralized version control systems

The next big problem people face is the need to interact with other developers. In order to deal with it, centralized version control systems (Centralized Version Control System, hereinafter CVCS) were developed. Systems such as CVS, Subversion, and Perforce use a single server that holds all versions of files, and a number of clients that retrieve files from this centralized repository. The use of CVCS has been the standard for many years.

This approach has many advantages, especially over local VCS. For example, all project developers know to some extent what each of them does. Administrators have full control over who can do what, and it's much easier to administer CVCS than it is to manage local databases on each client.

![Figure 2. Centralized version control](centralized.png)
Figure 2. Centralized version control

Despite this, this approach also has serious disadvantages. The most obvious downside is the single point of failure represented by the centralized server. If that server goes down for an hour, during that time no one will be able to use version control to save the changes they are working on, and no one will be able to share those changes with other developers. If the hard disk where the central database is stored is damaged and there are no timely backups, you will lose everything—the entire history of the project, not counting the single snapshots of the repository that were saved on the local machines of the developers. Local VCSs suffer from the same problem: when all project history is stored in one place, you risk losing everything.

4. Distributed version control systems

This is where Distributed Version Control System (DVCS) comes into play. In DVCS (such as Git, Mercurial, Bazaar or Darcs), clients don't just download a snapshot of all files (the state of the files at a particular point in time)—they copy the entire repository. In this case, if one of the servers through which the developers communicated dies, any client repository can be copied to another server to continue working. Each copy of the repository is a complete backup of all data.

![Figure 3. Distributed version control](distributed.png)
Figure 3. Distributed version control

Moreover, many DVCSs can interact with multiple remote repositories at the same time, so you can work with different groups of people using different approaches at the same time within the same project. This allows you to apply several development approaches at once, for example, hierarchical models, which is completely impossible in centralized systems.

