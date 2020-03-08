---
title: 'Using salt'
published: true
publish_date: '09-03-2020 12:09'
taxonomy:
    category:
        - Developer
---

# SaltStack

We manage our fleet of Raspberry Pi based devices using SaltStack. This is a client server based system where our cameras ('clients' or 'minions') connect to the server (“master”) and await commands.   

When using salt you need to remember: 
- You must accept a camera (minion) before you can use it. 
- Commands can only run on cameras when they are connected to the internet.   Commands are not saved to run next time the camera comes online. 
-  You only get to see the result of your command when the entire command is finished. 


## Basic usage 
> sudo salt {camera-name} {command}

eg to check you can ping the camera test-324. 
> sudo salt test-324 test.ping


## Run commands

|  Command  name |  Details |
|---|---|
| test.ping |  Use this to check you can communicate with a camera |
| cmd.run  {command} | Use this to run any command.|
| cmd.run  'ls /var/spool/cptv/failed-uploads' | See if there are recordings that failed to upload |
| cmd.run 'dpkg -l thermal*' | See what version of themal-recorder and thermal-uploader are running on the device |
| service.restart thermal-recorder | Restart the thermal-recorder service.  Likewise service.stop, service.restart and service.status all work in a similar way|
| systemd.enable modemd | Have the modemd automatically start at boot.   Likewise systemd.disable does the opposite|

## File commands

|  Command name  |  Details |
|---|---|
| file.append /etc/config.file “foo=bar” | Appends the line with 'foo=bar' to the config file |
| file.replace /etc/config.file “oldtext” “newtext” | Replaces the 'oldtext' with the 'newtext' in the file.|
| cp.push_dir /var/log ‘syslog*’ | Copies (pushes) the syslog files from the camera to the master.   You will find the files under “/var/cache/salt/master/minions/{camera-name}/files/”

There are [many more file functions](https://docs.saltstack.com/en/latest/ref/modules/all/salt.modules.file.html) available.

