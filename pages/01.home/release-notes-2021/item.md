---
title: 'Releases Notes for 2021'
published: true
category:
    - 'Project Updates'
---

This article documents the major changes for the Cacophony Project's
software updates each week. The latest updates are at the top of the
article.

# Software releases
## Friday 9th July
### Thermal Processing (v2.9.2)
- Hot fix for processing bad recording over and over again

## Monday 5th July
### Predator Classifier (v2.16.6)
- Inception v3 model

### Thermal Processing (v2.9.1)
- Allow all models to tag wallaby devices
- Fix bug with failed videos constantly retrying

## Tuesday 1st June
### Predator Classifier (v2.14.3)
- Support to run multiple models at once
- Support for toggling video disk caching via command line


## Thursday 15th April
### Browse (v2.33.1)
-Added "Missed recording" label

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
- Updated wallaby model, and add inception model for all labels

## Wednesday 31st March
### Thermal Processing (v2.8.0)
- Fix multiple animals not being tagged automatically

## Wednesday 17th March
### Predator Classifier (v2.11.1)
- Fixed bug where some clips weren't processing due to bad frames


## Friday 12th March
### Predator Classifier (v2.11.0)
- Updated cptv to faster version
- Fixed bug where some clips were not processing due to negative regions


## Friday 5th March
### Thermal Camera

- Write background into cptv file
- Remove edge pixels in background frame for motion detection
- Fix motion being detected after a zero pixel restart
- Management interface can now read salt nodegroup
- Added system power on and off events
- Added salt-updater cron job


## Monday 22nd February

### API server (v 5.14.2)
- Added Stations
- Updated visits algorithm
- Fixed alert emailing


### Browse (v2.30.0)
- Visits page updated to work with new format
- Added Stations


### Predator Classifier (v2.10.0)
- Fixed lepton3.5 tracking problems
- Added calibrating to video if ffc event has occurred
- Stop tracking when ffc events occur

## Wednesday 27th January
### Predator Classifier (v2.9.1)
- Use background frame when doing tracking


### Browse (v2.29.1)
- Visits page update to show actual tag under visit events
- Fix js bugs

### API server (v 5.12.1)
- Update visits page to use one tag per recording
