---
title: "Docstore"
date: "2016-06-16"
description: "Document(file) Storage abstraction for golang"
categories:
  - "project"
tags:
  - "go"
  - "storage"
  - "golang"
  - "io"
#titlecolor: "#ffab40" #ffab40
---
Document(file) Storage abstraction for golang


## Overview
 1. Single Basic Interface for storing and retrieving documents
 2. Store and retrieve documents based on keys
 3. Implementations
      1. Amazon S3
      - File system

## Getting Started

Installing:  
```
 go get github.com/dmashuda/docstore
```

## Configuring Credentials For AWS

Before using the SDK, ensure that you've configured credentials. The best
way to configure credentials on a development machine is to use the
`~/.aws/credentials` file, which might look like:

```
[default]
aws_access_key_id = AKID1234567890
aws_secret_access_key = MY-SECRET-KEY
```

You can learn more about the credentials file from this
[blog post](http://blogs.aws.amazon.com/security/post/Tx3D6U6WSFGOK2H/A-New-and-Standardized-Way-to-Manage-Credentials-in-the-AWS-SDKs).

Alternatively, you can set the following environment variables:

```
AWS_ACCESS_KEY_ID=AKID1234567890
AWS_SECRET_ACCESS_KEY=MY-SECRET-KEY
```


## Example

### Storage Creation

```
// Creates new Storer backed by an S3 Bucket
var storage docstore.Storer = docstore.BasicAws("us-east-1", "dmashuda-dev")

// Creates new Storer backed by a file system
var storage docstore.Storer = docstore.NewFileStore("/Volumes/storage")
```

### Storing a document
```
// Prepares putObj with ioreader and Identifier
file, _ := os.Open(fileName)
putObj := docstore.CreateObj{
  Identifier: fileName,
  Body:       file,
}
//store the photo
//errors ignored
id, err := storage.Put(putObj)
```

### Retrieving a document
```
getObj, _ := storage.Get(fileName)

newFile := os.Create("newFile.jpg")
defer newFile.Close()
numBytes, err := io.Copy(newFile, getObj.Body)
```


## Contributing
https://github.com/dmashuda/docstore/graphs/contributors
 - Pull requests welcome
 - Feel free to add new docstore.Storer Implementations


## License

Released under the [MIT License](https://github.com/jinzhu/gorm/blob/master/License).
