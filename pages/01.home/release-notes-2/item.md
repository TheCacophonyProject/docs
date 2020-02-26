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

Releases to our testing servers and devices are listed under the
"Testing" header while testing to production are listed under
"Production". Changes being tested generally end up in production the
following week.

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