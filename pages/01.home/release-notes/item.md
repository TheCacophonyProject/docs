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

## Week of 11 November

### Production

#### API Server

- CSV export timezone is now set to New Zealand
- added location to CSV export
- fixed up time formatting in CSV export
- max query limit for recordings is now 100,000 items

#### Browse Portal

- changed audio tags Done button to navigate to next recording
- CSV export will retrieve up to 100,000 entries instead of the current page

#### Upload Processing

- Automatic tags are now applied independently of other tracks

## Week of 4 November

### Production

#### Thermal Camera 

- Device ID is now stored included in CPTV files

#### python-cptv library

- Added device ID support
- Updated package description on PyPI

### Testing

#### API Server

- CSV export timezone is now set to New Zealand
- added location to CSV export
- fixed up time formatting in CSV export
- max query limit for recordings is now 100,000 items

#### Browse Portal

- changed audio tags Done button to navigate to next recording
- CSV export will retrieve up to 100,000 entries instead of the current page

#### Upload Processing

- Automatic tags are now applied independently of other tracks

#### Thermal Camera

- Fixed management interface speaker test that wasn't working for some cameras
- Updated management interface clock page and fixed time zone handling bug
- Allow current real-time clock status to be directly interrogated

## Week of 28 October

### Production

#### Thermal camera 

- Addressed a variety of issues with the value the Real Time Clock (RTC) is handled to work around kernel driver bugs. This makes the clock much more reliable. 
- When internet connectivity is available, the RTC is now synced as soon as internet time sync (NTP) is acheived to ensure the clock corrections are made as soon as possible.
- Fixed audio event reporting when cameras is offline.

### Testing

#### Thermal camera 

- Device ID is now stored included in CPTV files

## Week of 21 October

### Production

#### Thermal camera 

- Configuration overhaul: the way configuration on the camera is stored has been changed to support more flexible and robust updates, both locally via the management interface and remotely.

## Week of 14 October

### Production

#### Thermal camera 

- Remove last still snapshot on startup to avoid confusion when first viewing camera output using management interface

### Testing

#### Thermal camera 

- Configuration overhaul: the way configuration on the camera is stored has been changed to support more flexible and robust updates, both locally via the management interface and remotely.

## Week of 7 October

### Production

#### Browse Portal

- added delete button for audio recordings
- made thermal video tag names inconsistent (#254)
- code linting tweaks

#### API Server

- Normalise existing tag names to match recent browse changes

### Testing

#### Thermal camera 

- Remove last still snapshot on startup to avoid confusion when first viewing camera output using management interface

## Week of 2 October

### Production

#### Browse Portal

- Fix for: Recording selection preference is not applied to initial query ([#242](https://github.com/TheCacophonyProject/cacophony-browse/issues/242))
- Update mem dependency to address security vulnerabilty

#### Audiobait

- support offline operation
- check for new audio schedules more often so that new schedule updates are applied on the day that they're configured
- validate downloaded audio files to avoid use of corrupted files
- simplified download logic

#### Thermal camera 

- Support continuous recording mode (for tuning motion detection)

## Week of 23 September

### Testing

#### audiobait

- check for new audio schedules more often so that new schedule updates are applied on the day that they're configured
- validate downloaded audio files to avoid use of corrupted files
- simplified download logic

#### Browse Portal

- Fix for: Recording selection preference is not applied to initial query ([#242](https://github.com/TheCacophonyProject/cacophony-browse/issues/242))
- Update mem dependency to address security vulnerabilty

## Week of 16 September

### Production

#### API Server
 
* Added device query endpoint and token access and TTL
* Fixed sporadically failing device query tests
* Restore the legacy /api/v1/recordings/:devicename POST endpoint (required for older Sidekick versions)

#### Browse Portal

- Fix for animal field on search page sometimes not being populated
- Remember audio/video search preference
- Fix for "query description sometimes shows NaN"
- Fix for "Custom duration fields sometimes don't appear when they should"
- Expand Advanced search criteria if a non-default advanced criteria is in use

## Week of 9 September

### Production

#### API Server

- Return file size when retrieving recordings and audio bait files
- Enhancements for device rename/re-register
- Include tag confidence in recording queries again
- Small CSV export enhancements
- Address security vulnerability in eslint-utils

#### Management Interface

- Add device IDs to About page
- Support new device rename API

#### thermal-recorder

- Added ability to turn on and off based on sunset and sunrise times.
- Final changes for new device registration scheme
- Throttling of recordings is now slightly less aggressive


#### Upload Processing

- Extract latitude and longitude from CPTV files (where available)

### Testing

#### API Server

- Fix recording count returned by query API

#### Browse Portal

- Added more animal tags (wallaby etc)

#### Management Interface

- include Salt minion ID on About screen

## Week of 2 September

### Production

#### Browse Portal

- cleaned up layout of recording view, especially the tagging controls
- search results can be displayed as table view in addition to card view
- new video track scrubber control
- avoid broken image icon where map tile will go
- fix video tracks not displaying at a certain size (tablet-ish)

### Testing

#### API Server

- Return file size when retrieving recordings and audio bait files
- Enhancements for device rename/re-register
- Include tag confidence in recording queries again
- Small CSV export enhancements
- Address security vulnerability in eslint-utils

#### Management Interface

- Add device IDs to About page
- Support new device rename API

#### Upload Processing

- Extract latitude and longitude from CPTV files (where available)

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

- Added ability to turn on and off based on sunset and sunrise times.
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

#### Thermal Cameras

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
