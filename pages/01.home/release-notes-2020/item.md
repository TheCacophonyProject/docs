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

Releases to our testing servers and devices are listed under the
"Testing" header while testing to production are listed under
"Production". Changes being tested generally end up in production the
following week.

## Week of 20 January

### Production

#### Browse Portal

- Tidy up the groups and device Admin pages
- Added help for Visits feature
- Fixed bug with page not loading for some URLs
- Fixed bug with remembering preferred user playback speed

#### API Server

- Reduce bug and improve code maintenance and navigation by using TypeScript 
- Add specialised API to speed up beta power tagging feature
- Access tokens (JWT) support added to add/delete tag endpoints (for power tagging)
- Access tokens for recordings are now only computed if the recording exists
- Recording data is now deleted in the background at API call time, reducing the data that needs to be pruned later
- Internal `fileKey` and `rawFileKey` fields are now longer exposed by the external API
- Preserve API server Docker container after it stops so that logs are available for troubleshooting
- Ensure all thrown errors are Error subclasses

#### Upload Processing

- Pin to specific audio-analysis version to ensure consistent behaviour and support upgrades

#### Predator Classifier

- Use config.toml for configuration (on Raspberry Pi)
- Fixed bug where export would failed if clip was all preview
- Fixed bug where closing the MPEG creater  would fail if it was never used
- Support snapshot generation (for management interface)
- Fix time window calculation
- Support motion without running the classifier (for Raspberry Pi)
- Fixed invalid reference to configuration
- Fix location tuple
- Keep last frame in memory for management interface

## Week of 13 January

### Production

#### API Server

- Set longer request timeout for report endpoint

#### Browse Portal

- Added End User Agreement prompt

#### Thermal Camera

- When being requested to stay on during updates or maintenance,
  always stay on for the maximum requested time
- Added API for querying the software and API version
- Added rate limiting for camera snapshots
- Automatically retry previously failed video uploads if they might succeed

### Testing

#### Browse Portal

- Tidy up the groups and device Admin pages
- Added help for Visits feature
- Fixed bug with page not loading for some URLs
- Fixed bug with remembering preferred user playback speed

#### API Server

- Reduce bug and improve code maintenance and navigation by using TypeScript 
- Add specialised API to speed up beta power tagging feature
- Access tokens (JWT) support added to add/delete tag endpoints (for power tagging)
- Access tokens for recordings are now only computed if the recording exists
- Recording data is now deleted in the background at API call time, reducing the data that needs to be pruned later
- Internal `fileKey` and `rawFileKey` fields are now longer exposed by the external API
- Preserve API server Docker container after it stops so that logs are available for troubleshooting
- Ensure all thrown errors are Error subclasses

#### Upload Processing

- Pin to specific audio-analysis version to ensure consistent behaviour and support upgrades

#### Predator Classifier

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