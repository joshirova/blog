---
title: Scientific programming languages | Bash
subtitle: The programming language your grandmother wrote in. Bash - what is it?

# Summary for listings and search engines
summary: Welcome!

# Link this post with a project
projects: []

# Date published
date: '2023-05-12T00:00:00Z'

# Date updated
lastmod: '2023-05-12T00:00:00Z'

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
  - bash
categories:
  - post 4
---


## Overview

# The programming language your grandmother wrote in

Bash was created by Brian Fox (a legendary and underrated guy) and released in 1989 as an open source replacement for the 1976 Bourne Shell. Its name is an acronym for Bourne Again SHell.
If you're used to writing in any other programming language, bash (and shell scripts in general) won't be intuitive to you. The syntax is unmemorable, the variables are weird, the scope is a total mess, and the flow of control never does what you think it does.

As with CSS, I stopped being afraid to write bash scripts when I learned a few key things about it: how it works, what it's really good at, and how to get it to do what I need. I also ran into a lot of stupid little mistakes that I just had to memorize.

Shell scripting is a lot of fun once you master the basics! Nothing will make you feel like a more accomplished hacker than writing a wild one-liner that runs on the first try.
Note: I'm assuming you have some prior knowledge of programming and shell scripting. If you're just getting started, here's a good resource to get you started. I'm assuming you at least know how to use the terminal and the following commands: ls, cd, pwd, cat, grep and have written (or attempted to write) a script or two.

By the way, since this article is related to the world of Linux and operating systems, I have a note for those who have been dealing with these issues longer than me: it's okay (even recommended!) to correct me if I'm wrong, just be polite.
Versions

The shell scripting language that most of us are currently working with is the Mac and Linux version of bash used to emulate the terminal in /bin/bash.

Debian (and by extension Ubuntu and Linux Mint) now uses a different but mostly compatible shell scripting language (dash) for system tasks. Note. translator: so the author of the article claims, but I see the use of bash everywhere.

You can also install zsh as your main shell, which is similar to bash in general but has some differences.

Because of all these small variations, it's a good idea to put #!/bin/bash (or whatever shell scripting language you want to use) at the top of files to indicate that the shell script should use that specific language, and not which one. - or else from those installed on the server.

Specifying the shell language in the file header will make its behavior more predictable. For example, the answers on Stack Overflow usually assume that you are using bash.
Basics

Let's look at a few fundamental things first.

Shell scripts are essentially text streams that pass data between themselves. They use the Unix philosophy of being good at one task and merging tiny tools into larger programs in an industrial pipeline fashion. The result of the execution of each tool is passed to the input of the next one in order.

# Syntax

Bash uses a non-strict syntax; you can use a semicolon at the end of the line if you like, and the indentation doesn't affect how the code runs. There is a trap in the laxity of the syntax. The bash syntax is important and very specific. In addition, compared to other languages, syntax errors are difficult to diagnose.
It is very important to use spaces and semicolons correctly.

For example, you might get a "[grep isn't a valid command" error if you forget to put a space inside the square brackets [] or "Unexpected end of file" if you forget a semicolon after the {}.

When defining a variable, a space between the variable and the = sign and between the = sign and the value produces different results. There is an important difference between single quotes and double quotes.

Syntax errors always look like logical errors, making it difficult to spot typos.

# Structure

Shell scripts understand execution control statements: if statements, while loops, for loops, case statements, and so on.

Bash differs from other languages in terms of conditions and scopes. However, because bash is more focused on one-liners and one-time scripts, conditions are not used as often as in other languages.

Here is an example one-liner that uses execution control without any if statements:

tac ~/error.log\
| grep -m1 -E "Error|Running restart" \
| grep -q "Error" \
&& echo "Found error since last restart"

Note: \ denotes a line break, tac is similar to cat but outputs the file in reverse order.

It looks ugly but is effective and illustrates the strengths and weaknesses of shell scripting.

A bash script can be very short and hard to read. You can do a lot in a few lines, but when something breaks it can be hard to figure out why. This is a blessing and a curse. With great power, an ogre appears

