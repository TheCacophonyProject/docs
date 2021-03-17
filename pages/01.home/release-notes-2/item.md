---
title: 'Releases to Test Notes for 2020'
published: true
taxonomy:
    category:
        - 'Project Updates'
---

This article documents the major changes for the Cacophony Project's
software updates each week. The latest updates are at the top of the
article.
## Wednesday 17th March
### Predator Classifier (v2.11.1)
- Fixed bug where some clips werent processing due to bad frames

## Tuesday 9th March
### Predator Classifier (v2.11.0)
- Updated cptv to faster version
- Fixed bug where some clips werent processing due to negative regions


## Monday 22nd Febraury
### API server (v 5.14.2)
- Added Stations
- Updated visits algorithm

### Browse (v2.30.0)
- Visits page update to work with new format

## Monday 15th Febraury

### Predator Classifier (v2.10.0)
- Fixed lepton3.5 tracking problems
- Added calibrating to video if ffc event has occured
- Stop tracking when ffc events occur

## Friday 5th Febraury

### API server (v 5.13.0)
- Switch nodemailer to emailjs to get emails working

## Wednesday 27th January
### Predator Classifier (v2.9.1)
- Use background frame when doing tracking


### Browse (v2.29.1)
- Visits page update to show actual tag under visit events
- Fix js bugs

### API server (v 5.12.1)
- Update visits page to use one tag per recording

## Monday 18th January
### Predator Classifier (v2.8.1)
- Fix issues causing it not to classify some clips


## Monday 21st December
### Predator Classifier (v2.8.0)
- Update tracking algorithm


### Thermal Processing (v2.7.2)
- Fix to master tag process, so it only adds 1 tag per track


### Browse (v2.28.2)
- Fix to view as bar for admins

## Thursday 17th December
### Browse (v2.28.0)
- Visits page now links with device id, so prev/next buttons work
- Super users can now impersonate other users
- Added not identifiable badge for recordings

### API server (v 5.11.1)

- Added some super user operations: - Get users list - Authenticate as another user
- Add alerts 
- Fix Visit Grouping Incorrectly 
- Use master tag in visits calculation 

### Thermal Processing (v2.7.1)

- Added a config item that specifies how long to wait when the last poll showed there is nothing to process.
- Added config to give model tag precedences, so we can have one "master" tag for each track
- Added thermal entry to processing_TEMPLATE and updated processing.config accordingly


## Wednesday 9th December
### Browse (v2.27.1)
* Tagging interface for users has been improved.   Users are encouraged to confirm or reject AI tags.  
* Tagging interface now shows the actual tag for the user even if it isn't one of the default quick tags
* Admin devices page shows the software version (heart beat) info if the camera has sent this information to the server.   
* ORC group devices will not get wallaby as one of the quick tag buttons
* Vehicle tag now available in the additional tags menu. 

## Tuesday 8th December
### API server (v 5.10.2)
-Added ability to get latest events.

## Wednesday 2nd December
### API server (v 5.10.1)
Added ability to select events by type

## Friday 27th November
### API Server
- Visits page now groups future unidentified events properly

## Wednesday 25th November

### Thermal camera (v2.9.2)
- Fix for thermal recordings getting into a bad state, when a zero pixel was detected

### Browse Portal (v2.26.3)
- Thermal recordings now show one overall AI classification which uses different models for wallaby and non-wallaby projects
- Added unidentified, wallaby and rabbit icons.
- Analysis page links to Visits page not recordings. 
- Recordings card can now be opened in a new tab 
- Improved spinning icon
- Fixed disappearing tool tips

## Wednesday 28th September
### Predator Classifier (v2.7.1)
- Add support for lepton3.5

### Thermal camera (v2.9.1)
- Added support for lepton3.5 and removed threshold limit


## Thursday 1st September
### Browse Portal (v2.26.2)
- Visits no query on page load,
- Recordings table view has correct link
- Recordings table view order of columns changed
- Fixed recordings next/prev bug
- Default search period is 7 days.
- Fixed export no having search parameters

## Wednesday 24th September - Tuesday 1st October
### Thermal Processing (v2.6.0)
- Upload prediction info per frame

### Predator Classifier (v2.6.5)
- Add support for latest movement model

## Wednesday 9th September - Tuesday 15th
### Browse Portal (v2.26.0)
- Next button goes through videos with the search parameters, 
- Search url is readable/editable, 
- Can select time for custom time period on search
- Added cypress tags
- Reinstated delete button in the delete users for groups
- Analysis page waits until user selects a group before it gets results.  (To stop overloading the server). 


## Week of 13th July
### Browse Portal
Display tags and tag images properly

### Thermal Processing
- Added ability to ignore tags
- Added keras model support

## Week of 28th June

### API Server
- Make usernames, group names and devicenames case insensitive
- Added visits API end point
- Make Device name + Groups Unique
- Added reporting for event service issues

### Browse Portal
- Added csv export to the visits page
- Removed limit of number of visits and added load more visits button
- Added sound lures to the visits page

## Week of 16th March
### Browse Portal
Bring back search button/panel on mobile and tablet views
added support for multiple AI models

### Thermal Processing
Added ability to run multiple models

## Week of 2nd March
### Browse Portal
Fixed search but where page wasn't being reset when search criteria changed. 

### Thermal camera
 - Rebuilt recorder (to incorporate raw writer which is only for use with bolson)  - thermal-recorder(v2.5.0 -> v2.6.0)
 - Fixed bug so device config files are properly deleted when configuring a new device - device-register(v1.0.0 -> v1.1.0)
 - Updated modemd (this update was missed) - modemd (v1.0.0 - v1.1.1)
    - Rename setting and upgade go-config
    - Update loggind and require minimum connection time and max time between connections
    - Increase time between running lsusb to find modem to save energy 
    - Reduce logging

## Week of 24th February

### API Server
NA

### Browse Portal
NA

### Thermal camera
- Fix default SPI speed on camera

## Week of 17th February

### API Server
 - When pruning no longer required recordings from disk, wait 20 minutes between fetching the list and pruning objects.   This should give the recordings time to be processed. 


## Week of 10th February

### Thermal camera
-  Added API for getting and deleting events
-  Alerting for service failures

### API Server
- Avoid systemctl pager usage in postinstall script
- Restored missing data from audio bait schedule API
- Add systemError as tag type and update how JSONB are compared in sequelize

### Browse Portal
- Fix administration of groups

## Week of 3 February

### API Server
- Fix prune objects (error in config was preventing from running)

### Thermal camera
- Show last time software was updated in About Page

## Week of 27 January

No release

## Week of 20 January

### API Server

- Normalise "false positive" tag
- Fixed bulk tagging query returning archived tracks 
- Removed unused code
- Remove some unnecessary logs
- Restore GroupUsers for GET /api/v1/groups

### Browse Portal

- Tweaks for API changes
- Suppress additional unnecessary api requests.
- Adding support for bulk-tagging API
- Allow anyone to view bulk tagger
- Added tags for deer, sheep, and goat

### Upload Processing

- Cacophony Index fix for silent recordings: update correction curve so it is never negative

### Thermal Camera 

- Change thermal camera socket and metadata handling to support new camera types
- Show last timestamp update in management interface

## Week of 13 January

### Browse Portal

- Tidy up the groups and device Admin pages
- Added help for Visits feature
- Fixed bug with page not loading for some URLs
- Fixed bug with remembering preferred user playback speed

### API Server

- Reduce bug and improve code maintenance and navigation by using TypeScript 
- Add specialised API to speed up beta power tagging feature
- Access tokens (JWT) support added to add/delete tag endpoints (for power tagging)
- Access tokens for recordings are now only computed if the recording exists
- Recording data is now deleted in the background at API call time, reducing the data that needs to be pruned later
- Internal `fileKey` and `rawFileKey` fields are now longer exposed by the external API
- Preserve API server Docker container after it stops so that logs are available for troubleshooting
- Ensure all thrown errors are Error subclasses

### Upload Processing

- Pin to specific audio-analysis version to ensure consistent behaviour and support upgrades

### Predator Classifier

- Use config.toml for configuration (on Raspberry Pi)
- Fixed bug where export would failed if clip was all preview
- Fixed bug where closing the MPEG creater  would fail if it was never used
- Support snapshot generation (for management interface)
- Fix time window calculation
- Support motion without running the classifier (for Raspberry Pi)
- Fixed invalid reference to configuration
- Fix location tuple
- Keep last frame in memory for management interface

##### 