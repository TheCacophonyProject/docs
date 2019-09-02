---
title: 'Releases Notes for 2019'
published: true
taxonomy:
    category:
        - 'Project Updates'
---

This article documents the major changes for the Cacophony Project's
software updates each week. The latest updates are at the top of the
article.

Releases to our testing servers and devices are listed under the
"Testing" header while testing to production are listed under
"Production". Changes being tested generally end up in production the
following week.

## Week of 2 September

### Production

#### Browse Portal

- cleaned up layout of recording view, especially the tagging controls
- search results can be displayed as table view in addition to card view
- new video track scrubber control
- avoid broken image icon where map tile will go

### Testing

#### API Server

- Return file size when retrieving recordings and audio bait files
- Enhancements for device rename/re-register
- Include tag confidence in recording queries again
- Small CSV export enhancements
- Address security vulnerability in eslint-utils

#### Browse Portal

- Fix video tracks not displaying at a certain size (tablet-ish)

#### Management Interface

- Add device IDs to About page
- Support new device rename API

## Week of 26 August

### Production

#### API Server

- Added API for renaming devices
- Added tracking of device identity history
- Backend support for CSV export
- Allow `reprocess` API to work for audio recordings as well as thermal video
- Authentication refactoring

#### Browse Portal

- Significant reworking of recordings query page
   - Search criteria now on the left hand side
   - Cleaner search results display
   - Mobile friendly layout
   - "Timeline" to highlight the date and time
- Deleting recordings now triggers navigation to the next recording
- Fixed a variety of issues related to tooltip positioning
- Steamlined layout of recording view
- Show recording buttons on small screens too
- Restore recording comment functionality
- Fix unnecessary page refreshes when tags are added
- Fix playback restarts when tags are added
- CSV export
- Cleaned up recordings page especially around tagging
- Fixed up recording page layout

### Testing

#### Browse Portal

- cleaned up layout of recording view, especially the tagging controls
- search results can be displayed as table view in addition to card view
- new video track scrubber control
- avoid broken image icon where map tile will go

#### Sidekick App

- Improved detection of nearby cameras
- More robust location determination

#### Bird Monitor

- New randomised sampling schedule to provide higher quality bird population data

#### Thermal camera

- Added ability to turn on and off based on sunset and sunset times.
- Updates throughout onboard services to support new identity changes
- More robust audio file download logic
- New management interface "About" page - shows software versions and device ids

## Week of 19 August

### Testing

#### Browse Portal

- CSV export
- Cleaned up recordings page especially around tagging
- Fixed up recording page layout

#### API Server

- Added API for renaming devices
- Added tracking of device identity history
- Backend support for CSV export
- Allow `reprocess` API to work for audio recordings as well as thermal video
- Authentication refactoring

## Week of 12 August

### Testing

#### Browse Portal

- Significant reworking of recordings query page
   - Search criteria now on the left hand side
   - Cleaner search results display
   - Mobile friendly layout
   - "Timeline" to highlight the date and time
- Deleting recordings now triggers navigation to the next recording
- Fixed a variety of issues related to tooltip positioning
- Steamlined layout of recording view

#### API Server

- Added API for renaming devices
- Added tracking of device identity history

## Week of 5 August

### Production

#### Browse Portal

- Work around flickering Confirm Tag popover
- Address security vulnerability in dependency

#### Audio Bait UI

- Fixed doubled up device and schedule entries

## Week of 29 July

### Production

#### thermal-recorder

- Simplified and cleaned up throttling of recordings to make this feature easier to understand and configure.
- Throttling can now be disabled on a per-device basis.

#### cacophony-api

- Require that group names are unique

## Week of 22 July

### Production

#### cacophony-api

- Archive legacy recording tags when reprocessing recordings for track based tagging

#### management-interface

- New "About" screen which shows installed package versions

#### thermal-recorder

- Extend application watchdog period to allow for longer camera initialisation times

## Week of 15 July

### Production

#### audiobait

- Fixed API URL bug when requesting new schedule

#### browse portal (cacophony-browse)

- Updated external dependencies to address security vulnerabilities
- Fixed mis-alignment when drawing track outlines over videos

#### cacophony-api

- Automated daily pruning of recording data for deleted recordings
- Addressed security vulnerabilities in upstream dependencies
- Allow larger HTTP request bodies to support large POSTs containing thermal video track data

#### cacophony-processing

- Upload processed recordings with a type based object key (to match changes in cacophony-api)

#### management-interface

- Added new page for viewing and setting the hardware clock
- Clean up the layout of the WiFi configuraiton screen
- Added new `/device-info` API to allow Sidekick to retrieve identifiers for device

## Week of 8 July

### Production

#### attiny-controller

- added support for reading battery voltage (when hardware supports it)
- added support for indicating WiFi connectivity via status LED

#### modemd

- This is a new service which runs on the thermal camera which will
  save power by turning on the 3G modem on demand. The 3G modem can be
  a major source of power consumption so by only turning it on
  occasionally when it's needed, battery life can be extended.
- Other services have been updated to interact with modemd (using
  D-Bus) when they require internet connectivity (thermal-uploader,
  event-reporter, audiobait)

#### thermal-recorder

- Added new motion detection debug logging feature
- Fixed logging in motion detector

#### device identity API changes

- Initial changes to update the API server and the project's various API clients to base API interaction around an integer id instead of the device friendly name.
- This will end users to easily rename devices themselves, as well as streamlining device production and monitoring.
