---
title: 'Releases Notes for 2021'
published: true
taxonomy:
category:
- 'Project Updates'
---

This article documents the major changes for the Cacophony Project's
software updates each week. The latest updates are at the top of the
article.

# Software releases

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
