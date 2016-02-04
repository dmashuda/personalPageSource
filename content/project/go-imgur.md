---
title: "Go-Imgur"
date: "2016-02-01"
description: "A basic imgur api client for go"
cardbackground: "#1565C0"
repo: "https://github.com/dmashuda/go-imgur"
"author":
  description: "Software Engineer"
  email: "dmashuda@ycp.edu"
  github: "https://github.com/dmashuda/"
  name: "Daniel Mashuda"
  website: "danmashuda.com"
categories:
  - "project"
tags:
  - "go"
  - "imgur"
  - "api"
  - "golang"
#titlecolor: "#ffab40" #ffab40
---

A basic api client for [imgur](https://api.imgur.com/). Currently I have only implemented the features of the imgur api that I use for other projects.

If you would like another piece of functionality implemented, open an [issue](https://github.com/dmashuda/go-imgur/issues/new) or implement it yourself and submit a pull request

## Installation:
{{< highlight go >}}
    go get github.com/dmashuda/go-imgur     
 {{< /highlight >}}


## Example Usage:
#### Creating a Client:
    {{< highlight go >}}
    client := imgur.NewClient(clientID)   
    {{< /highlight >}}
*clientID is issued by imgur on a per application basis*

#### Retrieving album information:
{{< highlight go >}}
    aww, err := client.GetAlbum("/gallery/r/CorgiGifs", 0, 20)    
    {{< /highlight >}}
