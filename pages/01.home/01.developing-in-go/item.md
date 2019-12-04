---
title: 'Developing in GO'
published: true
date: '05-12-2019 10:44'
publish_date: '05-12-2019 10:43'
taxonomy:
    category:
        - Developer
        - 'Thermal Camera'
---

The Cacophony project uses go for writing code to run on the thermal camera raspberry PI.  

Here are some instructions for setting up GO for development. 

## Set up
Before you begin you define your $GOPATH in your environmental variables.   This is the base directory where all GO projects will be installed into.   
```console
> set GOPATH='/cacophony/go'
```

## New Project
To clone a new project you must do it using go
```console
> go get github.com/TheCacophonyProject/<projectname>    
```
    
To build the project (to run on your development environment) first make sure you get all the go dependences and then run the build command
```console
> go get ./...
> go build ./...
```
If you want to build for the thermal-camera RaspberryPi hardware then run
```console
> GOOS=linux GOARCH=arm GOARM=7 go build ./...
```
## Working with your own repository fork
When developing for Cacophony, you should be commiting all new code to your own development fork.  However, you can't directly check out your new fork as the code won't be in the correct place working with your other GO projects.  
    
To develop on your fork the best solution is to add a new remote to your git project.   For example you can add your fork
```console
>  git remote add myfork git@github.com:<username>/<project>.git
```
And then you are able to create branches as normal.   Just remember to you push your changes directly into your fork
```console
> git checkout -t -b awesome-feature
> git push myfork
```
For more explaination on why this is required and how to do this, have a look at Scott Mansfield's blog on [Working With Forks in Go](https://blog.sgmansfield.com/2016/06/working-with-forks-in-go/)