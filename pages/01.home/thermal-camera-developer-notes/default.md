---
title: 'Thermal camera developer notes'
published: true
taxonomy:
    category:
        - Developer
        - 'Thermal Camera'
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
|/var/log/system | Latest log file containing output from our services. (Other system.n.* files in the same directory are older log files) |

# Installation details

Our Raspberian Software is packaged into .DEB files and installed using **systemd**.   This means that most applications will automatically start when the thermal camera is powered up.  Some will also restart when they crash. 

## How to install our DEB packages

To install one of our programs on your raspberry Pi:
1.  Download the ***._arm.deb** file from the github release page to your Pi
2.  Install the package using dpkg -i

For example to install modemd, v1.1.0
```
> wget https://github.com/TheCacophonyProject/modemd/releases/download/v1.1.0/modemd_1.1.0_arm.deb
> sudo dpkg -i modemd_1.1.0_arm.deb
```

To see what version of software is currently installed you can use dpkg -l. 

For  modemd you can use:
```
> dpkg -l modemd
```

## Finding the service's name

If you want to manually start/stop an application you can use the **sudo systemctl start someName.service** command.   

To use this command you will need to know the service name of the application.   Look in the application's git repository, under the **_ release** directory to find this name.   Some github projects install more than one service. 

Eg. if there is a _thermal-recorder.service_ file there then the service is called _thermal-recorder.service_

## Useful commands
|Command|Description|
|---|---|
| sudo systemctl start <service> |  Start a service |
| sudo systemctl stop <service>|  Stop a service |
| systemctl status <service>| Get information about whether a service is running |
| journalctl -u <service> -f | Show a rolling (updating) log of for the service specified |

For a list of more commands read [Systemd Essentials](https://www.digitalocean.com/community/tutorials/systemd-essentials-working-with-services-units-and-the-journal)