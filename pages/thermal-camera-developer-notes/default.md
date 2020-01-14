---
title: 'Thermal camera developer notes'
---

Here you will find information to help you navigate and debug any device on which you have installed our thermal-camera software. 

# Software
Our thermal camera software consists of many [software programs](https://github.com/search?q=topic%3Athermal-camera+org%3ATheCacophonyProject+fork%3Atrue) that each do a part of the work of the thermal camera.   

# Useful paths

|Path|Description|
|---|---|
|/etc/cacophony/config.toml | Configuration file for cacophony software |
|/var/spool/cptv | CPTV files that haven't been uploaded are stored here |
|/var/spool/cptv/failed-uploads | CPTV files are moved here after multiple attempts have been made to upload them |
|/usr/bin | Our executables are installed here |
|/etc/systemd/system/ | Installation information for each service |

# Installation details

Our Raspberian Software .DEB files  is installed using **systemd**.   This means that most applications will automatically start when the thermal camera is powered up.  Some will also restart when they crash. 

## Finding the services name

If you want to manually start/stop an application you can use the **sudo systemctl start someName.service** command.   

To use this command you will need to know the service name of the application.   Look in the application's git repository, under the **_ release** directory to find this name.   

Eg. if there is a _thermal-recorder.service_ file there then the service is called _thermal-recorder.service_

## Useful commands
|Command|Description|
| sudo systemctl start <service> |  Starts a service |
| sudo systemctl stop <service>|  Stops a service |
| systemctl status <service>| Tells you whether a service is running |
| journalctl -u <service> -f | Shows a rolling (updating) log of all the log information for the service specified |

For a list of more commands read [Systemd Essentials](https://www.digitalocean.com/community/tutorials/systemd-essentials-working-with-services-units-and-the-journal)