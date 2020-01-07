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

