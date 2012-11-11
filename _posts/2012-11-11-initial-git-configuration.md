---
layout: post
title: "Initial Git configuration"
description: "abc"
category: 
tags: [git]
tagline:
published: false
---
{% include JB/setup %}


http://git-scm.com/book/ch1-5.html

## Information to identify Yourself

    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com

## Preferred editor

	git config --global core.editor emacs

## Diff/Merge tool

	git config --global merge.tool kdiff3

## Prevent some possible problems

push.default

## Useful configuration

core.excludesfile
commit.template


## Useful commands

http://oli.jp/2012/git-powerup/
word diff
log --decorate
status -s -b
