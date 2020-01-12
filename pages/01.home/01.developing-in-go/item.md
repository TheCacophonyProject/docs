---
title: 'Developing in Go'
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

## Building projects
If you want to build for the thermal-camera RaspberryPi hardware then run
```console
> GOOS=linux GOARCH=arm GOARM=7 go build ./...
```

## Testing
You can run the tests for any project and its sub-folders by running
```console
> go test ./...
```

## Test local changes in another module
Sometimes you want to test changes you have made in a another module which have yet made it to the master branch.  

For example you may have edited go-config, and want to use the new config in your go program _thermal-stuff_.   If that is the case you need to edit the _go.mod_ of _thermal-stuff_  and add a replace statement like this:
```console
go.mod:
...
replace https://github.com/TheCacophonyProject/go-config => /path/on/your/machine/go-config
```
This will tell go to look at your local path instead of pulling the module from the github. 

Be careful not to checkin in the modified _go.mod_ or it will fail the tests. 

For more details see [How to test local changes with go mod](https://medium.com/@teivah/how-to-test-a-local-branch-with-go-mod-54df087fc9cc)




