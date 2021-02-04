---
title: 'Releases Notes for 2020'
published: true
taxonomy:
    category:
        - 'Project Updates'
---

This article documents the major changes for the Cacophony Project's
software updates each week. The latest updates are at the top of the
article.

# Software releases
## Wednesday 27th January
### Predator Classifier (v2.9.1)
- Use background frame when doing tracking


### Browse (v2.29.1)
- Visits page update to show actual tag under visit events
- Fix js bugs

### API server (v 5.12.1)
- Update visits page to use one tag per recording


## Monday 21st December
### API server (v 5.11.1)
- Added some super user operations: - Get users list - Authenticate as another user
- Add alerts 
- Fix Visit Grouping Incorrectly 
- Use master tag in visits calculation 


### Thermal Processing (v2.7.2)
- Added a config item that specifies how long to wait when the last poll showed there is nothing to process.
- Added config to give model tag precedences, so we can have one "master" tag for each track
- Added thermal entry to processing_TEMPLATE and updated processing.config accordingly


### Browse (v2.28.2)
- Visits page now links with device id, so prev/next buttons work
- Super users can now impersonate other users
- Added not identifiable badge for recordings


## Wednesday 16th December
#### Browse (v2.27.1)
* Tagging interface for users has been improved.   Users are encouraged to confirm or reject AI tags.  
* Tagging interface now shows the actual tag for the user even if it isn't one of the default quick tags
* Admin devices page shows the software version (heart beat) info if the camera has sent this information to the server.   
* ORC group devices will not get wallaby as one of the quick tag buttons
* Vehicle tag now available in the additional tags menu. 
* Wallaby quick tag shows on Wallaby cameras

#### API server (v5.10.2)
* Can select events by type, and can choose to get the most recent events first. 


## Tuesday 8th November
### Thermal Camera (v2.9.2)
- Added support for lepton3.5
- Removed maximum temperature threshold.
- Restart camera on bad first pixel


## Monday 30th November
### API Server (v5.10.0)
- Visits page now groups future unidentified events properly

## Wednesday 25th November

### Browse Portal (v2.26.3)
- Thermal recordings now show one overall AI classification which uses different models for wallaby and non-wallaby projects
- Added unidentified, wallaby and rabbit icons.
- Analysis page links to Visits page not recordings. 
- Recordings card can now be opened in a new tab 
- Improved spinning icon
- Fixed disappearing tool tips

## Friday 13th November
### API Server
- Allow metadata to be uploaded with raw cptv

## Wednesday 28th September
### Predator Classifier (v2.7.1)
- Add support for lepton3.5


## Thursday 1st September
### Browse Portal (v2.26.2)
- Visits no query on page load,
- Recordings table view has correct link
- Recordings table view order of columns changed
- Fixed recordings next/prev bug
- Default search period is 7 days.
- Fixed export no having search parameters

## Wednesday 24th September - Tuesday 1st October
### Predator Classifier (v2.6.4)
- Add support for latest movement model

## Wednesday 16th September
### Browse Portal (v2.26.0)
- Next button goes through videos with the search parameters, 
- Search url is readable/editable, 
- Can select time for custom time period on search
- Added cypress tags
- Reinstated delete button in the delete users for groups
- Analysis page waits until user selects a group before it gets results.  (To stop overloading the server). 

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
## Week of 24th February

### API Server
- When pruning no longer required recordings from disk, wait 20 minutes between fetching the list and pruning objects. This should give the recordings time to be processed. 

### Browse Portal
NA

### Thermal camera
NA

## Week of 17th February

### API Server
- Avoid systemctl pager usage in postinstall script
- Restored missing data from audio bait schedule API
- Add systemError as tag type and update how JSONB are compared in sequelize

### Browse Portal
- Fix administration of groups


## Week of 10th February

### API Server
- Fix prune objects (error in config was preventing from running)

### Thermal camera
- Show last time software was updated in About Page


## Week of 3rd February

No release was done

## Week of 27th January

### API Server

- Normalise "false positive" tag
- Fixed bulk tagging query returning archived tracks 
- Removed unused code
- Remove some unnecessary logs
- Restore GroupUsers for GET /api/v1/groups
- Restore GroupUsers manipulation
- Add back devicename to group info.
- Fix duplicate recording removal

### Browse Portal

- Tweaks for API changes
- Suppress additional unnecessary api requests.
- Adding support for bulk-tagging API
- Allow anyone to view bulk tagger
- Added tags for deer, sheep, and goat
- Fix issues with users under groups in the Admin area
- Tidy up Power Tagger action buttons
- Add delete button to Power Tagger page for superusers

### Upload Processing

- Cacophony Index fix for silent recordings: update correction curve so it is never negative

### Thermal Camera 

- Change thermal camera socket and metadata handling to support new camera types
- Show last timestamp update in management interface

## Week of 20 January

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

## Week of 13th January

### API Server

- Set longer request timeout for report endpoint

### Browse Portal

- Added End User Agreement prompt

### Thermal Camera

- When being requested to stay on during updates or maintenance,
  always stay on for the maximum requested time
- Added API for querying the software and API version
- Added rate limiting for camera snapshots
- Automatically retry previously failed video uploads if they might succeed