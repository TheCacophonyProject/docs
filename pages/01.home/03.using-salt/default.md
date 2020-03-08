---
title: 'Using salt'
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

|  command  |  details |
|---|---|
| test.ping |  use this to check you can communicate with a camera |
| cmd.run  {command} | use this to run any command.|
| cmd.run  'ls /var/spool/cptv/failed-uploads' | see if there are recordings that failed to upload |
| cmd.run 'dpkg -l thermal*' | see what version of themal-recorder and thermal-uploader are running on the device |
