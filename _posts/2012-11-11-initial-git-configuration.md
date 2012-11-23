---
layout: post
title: "Initial Git configuration"
description: "Some useful Git customization"
category: 
tags: [git]
tagline:
published: true
---
{% include JB/setup %}

After Git is set up it is good idea to customize it.

## Information to identify Yourself

    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com

## Preferred editor

	git config --global core.editor nano

## Diff/Merge tool

	git config --global merge.tool kdiff3

## Prevent some possible problems

Defines the action git push should take if no refspec is given on the command line, no refspec is configured in the
remote, and no refspec is implied by any of the options given on the command line. "Current" means push the current
branch to a branch of the same name.

    git config --global push.default current

## Useful configuration

Here are some useful configuration values described.

In addition to .gitignore (per-directory) and .git/info/exclude, git looks into this file for patterns of files which
are not meant to be tracked. "~/" is expanded to the value of $HOME and "~user/" to the specified user’s home directory

    git config --global core.excludesfile <path to file>

Specify a file to use as the template for new commit messages. "~/" is expanded to the value of $HOME and "~user/"
to the specified user’s home directory.

    git config --global commit.template <path to file>

## Useful commands

Here are some useful commands described

Displaying console graph log

    git log --oneline --graph --decorate

Show a word diff highlighting changed words using only colors

    git diff --word-diff=color
