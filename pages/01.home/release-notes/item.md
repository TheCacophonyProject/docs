---
title: 'Releases Notes for 2019'
published: true
taxonomy:
    category:
        - 'Project Updates'
---

This article documents the major changes for the Cacophony Project's software updates each week. The latest updates are at the top of the article.

## Week of 29 July 2019

### thermal-recorder

- Simplified and cleaned up throttling of recordings to make this feature easier to understand and configure.

### cacophony-api

- Require that group names are unique

## Week of 22 July 2019

### cacophony-api

- Archive legacy recording tags when reprocessing recordings for track based tagging

### management-interface

- New "About" screen which shows installed package versions

### thermal-recorder

- Extend application watchdog period to allow for longer camera initialisation times

## Week of 15 July 2019

### audiobait

- Fixed API URL bug when requesting new schedule

### browse portal (cacophony-browse)

- Updated external dependencies to address security vulnerabilities
- Fixed mis-alignment when drawing track outlines over videos

### cacophony-api

- Automated daily pruning of recording data for deleted recordings
- Addressed security vulnerabilities in upstream dependencies
- Allow larger HTTP request bodies to support large POSTs containing thermal video track data

### cacophony-processing

- Upload processed recordings with a type based object key (to match changes in cacophony-api)

### management-interface

- Added new page for viewing and setting the hardware clock
- Clean up the layout of the WiFi configuraiton screen
- Added new `/device-info` API to allow Sidekick to retrieve identifiers for device

## Week of 8 July 2019

### attiny-controller

- added support for reading battery voltage (when hardware supports it)
- added support for indicating WiFi connectivity via status LED

### modemd

- This is a new service which runs on the thermal camera which will save power by turning on the 3G modem on demand. The 3G modem can be a major source of power consumption so by only turning it on occasionally when it's needed, battery life can be extended.
- Other services have been updated to interact with modemd (using D-Bus) when they require internet connectivity (thermal-uploader, event-reporter, audiobait)

### thermal-recorder

- Added new motion detection debug logging feature
- Fixed logging in motion detector

### device identity API changes

- Initial changes to update the API server and the project's various API clients to base API interaction around an integer id instead of the device friendly name.
- This will end users to easily rename devices themselves, as well as streamlining device production and monitoring.