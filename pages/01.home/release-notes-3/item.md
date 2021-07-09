---
title: 'Releases to Test Notes for 2021'
published: true
category:
    - 'Project Updates'
---

This article documents the major changes for the Cacophony Project's
software updates each week. The latest updates are at the top of the
article.
## Friday 9th July
### Thermal Processing (v2.9.2)
- Hot fix for processing bad recording over and over again


## Friday 7th May
### Predator Classifier (v2.13.2)
- Support to run multiple models at once
- Support for toggling video disk caching via command line

### API (v5.20.0)
- Fix recordings csv
- Only alert on master tags
- Alerts will link to a specific track id


### Thermal Processing (v2.8.2)
- Classify videos with disk caching only if longer than 4 minutes (Should speed up processing times)

## Wednesday 14th April
### Browse (v2.33.1)
-Added "Missed recording" label

## Tuesday 13th April
### Browse (v2.33.0)
- Update insecure npm dependencies
- Fix broken device page

### API (v5.17.0)
- Improve visits query speed (especially for audio baits)
- Device-in-group request added
- Fixed api-doc

## Wednesday 08th April
### Predator Classifier (v2.12.0)
- Support for newer models


## Wednesday 24th March
### Thermal Processing (v2.8.0)
- Fix multiple animals not being tagged automatically


### Browse (v2.31.0)
- Show device events list
- Display our single AI master tag everywhere in the UI
- Restore ability to tag multiple animals in a video
- Added ability for super-admin users to view just their own groups and devices
- Ignore inactive devices

### API Server (v5.15.0)
- Super-users can opt into viewing only their own groups and devices
- Alerts for stopped devices

## Wednesday 17th March
### Predator Classifier (v2.11.1)
- Fixed bug where some clips weren't processing due to bad frames

## Tuesday 9th March
### Predator Classifier (v2.11.0)
- Updated cptv to faster version
- Fixed bug where some clips weren't processing due to negative regions


## Monday 22nd February
### API server (v 5.14.2)
- Added Stations
- Updated visits algorithm

### Browse (v2.30.0)
- Visits page update to work with new format

## Monday 15th February

### Predator Classifier (v2.10.0)
- Fixed lepton3.5 tracking problems
- Added calibrating to video if ffc event has occured
- Stop tracking when ffc events occur

## Friday 5th February

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
