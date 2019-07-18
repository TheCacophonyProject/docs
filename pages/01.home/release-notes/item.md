---
title: 'Releases Notes for 2019'
published: false
taxonomy:
    category:
        - 'Project Updates'
---

This article documents the major changes for the Cacophony Project's software updates each week.

# Week of 15 July 2019



# Week of 8 July 2019

## attiny-controller

- added support for reading battery voltage (when hardware supports it)
- added support for indicating WiFi connectivity via status LED

## modemd

- This is a new service which runs on the thermal camera which will save power by turning on the 3G modem on demand. The 3G modem can be a major source of power consumption so by only turning it on occasionally when it's needed, battery life can be extended.
- Other services have been updated to interact with modemd (using D-Bus) when they require internet connectivity (thermal-uploader, event-reporter, audiobait)
-