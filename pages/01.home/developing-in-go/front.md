---
title: 'Developing in GO'
---

The Cacophony project uses go for writing code to run on the thermal camera raspberry PI.  

Here are some instructions for setting up GO for development. 

## Set up
Before you begin you define your $GOPATH in your environmental variables.   This is the base directory where all GO projects will be installed into.   
eg.  Run >> set GOPATH='/cacophony/go'

## New Project
To clone a new project using git you must do it using go
> go get github github.com/TheCacophonyProject/<projectname>    
    
To build the project first make sure you get all the go dependences and then run the build command
> go get ./...
> go build

If you want to build for the thermal-camera RaspberryPi hardware then run
> GOOS=linux GOARCH=arm GOARM=7 go build 

## Working with your own repository fork
When developing for Cacophony, you should be commiting all new code to your own development fork.  However, you can't directly check out your new fork as the code won't be in the correct place working with your other GO projects.  
    
To develop on your fork the best solution is to add a new remote to you git project.   For example you can add your fork
    
>  git remote add myfork git@github.com:<username>/<project>.git


And then when you push your work push it into your fork
    
> git 