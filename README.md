dynocator
=========

[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/ahsanulhaque/dynocator?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

A lightweight blog/website engine written in Go

[![wercker status](https://app.wercker.com/status/31c879f3e09f9c126fc1f8b41d6c83cd/s "wercker status")](https://app.wercker.com/project/bykey/31c879f3e09f9c126fc1f8b41d6c83cd)
[![Build Status](https://travis-ci.org/ahsanulhaque/dynocator.svg?branch=master)](https://travis-ci.org/ahsanulhaque/dynocator)


## Some Screenshots

![Posts](http://i.imgur.com/FpXAw0P.png)

![EditPost](http://i.imgur.com/soOFQ0h.png)

## Overview

dynocator is a static blog/website engine with an WYSIWYG editor for folks who don't want to write Markdown posts. Some features are:
- Uses [Froala](https://editor.froala.com) editor to write/edit posts
- Has an admin section to add/remove/edit posts
- Support for drafts
- Categories
- Watches `posts` folder for changes so that new posts are automagically converted to static html files
- Can either create a blog index page from posts, or use one of the posts as the main index page
- Uses Go's cool templates to make simple but powerful frontend

## Installing dynocator
To use staticator, you need to have Go installed on yout suystem. Once that's taken care of, do this to install staticaor:
```
go get github.com/ahsanulhaque/dynocator
```

To make the dynocator executable available to from anywhere, include it in your path(in .bashrc or .zshrc) like so:
```
export PATH=$PATH:$GOPATH/bin
```

## Setting up dynocator
dynocator requires a `config.toml` file for configuration. Create a `config.toml` file in your project directory containing:
```
baseurl="http://localhost:1414"
title="My Beautiful Site"
templates="templates"
posts="posts"
public="public"
admin="admin"
metadata="metadata"
index="default"
```
Your project directory should have the following structure:
```
posts/
public/
public/static
templates/
admin/
metadata/
```
Note that your static assets like css/js should be in `public/static`

## Deploying dynocator

You should deploy dynocator behind nginx as a reverse proxy for best results.

