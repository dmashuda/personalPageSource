---
title: "Hugo: First Impressions"
description: "Hugo: First Impressions"
date: "2016-01-30"
categories:
    - "post"
tags:
    - "hugo"
    - "opinion"
cardthumbimage: "/images/default.jpg" #optional: default solid color if unset
cardheaderimage: "/images/default.jpg" #optional: default solid color if unset
cardbackground: "#263238" #optional: card background color; only shows when no image specified
#cardtitlecolor: "#fafafa" #optional: can be changed to make text visible over card image
"author":
    name: "Daniel Mashuda"
    description: "Software Engineer"
    website: "http://danmashuda.com"
    email: "dmashuda@ycp.edu"
    github: "https://github.com/"
    image: "/images/avatar.png"
---


[Hugo](https://gohugo.io/) is a static site generator. It is very flexible and
members of the community contribute high quality themes so that those of us
without a creative bone in our body can generate websites with high visual quality

#### Why a static site generator?

A static site generator has the benefits of a view templating system, but the
cost of assembly for the template is completed before the site is deployed. This
allows for effective static hosting and no cost caching. One caveat of static site generators
is that the site must be re-generated after every change.

For the case of my website, which i change infrequently, hugo is a perfect fit.
I do not have to have a database that I have to manage. I do not have an application
server that I manage. All of my content for the pages on my site are written in markdown,
so formatting is simple. I statically host my site on [github pages](https://pages.github.com/) for free.  
