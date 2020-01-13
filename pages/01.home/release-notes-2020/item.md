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
