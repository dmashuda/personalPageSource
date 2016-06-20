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
 - Single Basic Interface for storing and retrieving documents
 - Store and retrieve documents based on keys
 - Implementations
  - [Amazon S3](https://github.com/docstore/s3storage)
  - File system

## Getting Started

Installing:  
```
 go get github.com/docstore/storage
```

## Example

### Storage Creation

```
// Creates new Storer backed by a file system
var storage docstore.Storer = docstore.NewFileStore("/Volumes/storage")
```

### Storing a document
```
// Prepares putObj with ioreader and Identifier
file, _ := os.Open(fileName)
putObj := docstore.CreateObj{
  Identifier: fileName,
  ReadSeeker: file,
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
defer getObj.Close()
numBytes, err := io.Copy(newFile, getObj)
```


## Contributing
https://github.com/docstore/storage/graphs/contributors
 - Pull requests welcome
 - Feel free to add new docstore.Storer Implementations


## License

Released under the MIT License
