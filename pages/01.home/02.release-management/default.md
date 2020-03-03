---
title: 'Release Management'
---

This document describes the weekly process of promoting software from development -> test ->  production.  It is only of interest to the core team or anyone wanting to maintain their own cacophony server.  

This document covers server software and the thermal camera software.   It does not currently explain the release processes for our two android apps - birdmonitor and sidekick. 

This document is written to be followed from top to bottom each release day.  **Before starting the process make sure the previous release in test has been pushed to production. **

## Release new software to test
Start by releasing software on the servers and then the camera software.

### Server Packages
1. Run the find-unreleased tool on the Salt server (this can also be run locally if you have ops-tools). This will highlight any of Cacophony Project software with changes that haven't made it into a release yet.
2. For each server package that has unreleased changes:
  1. [Create a release in Github](/home/creating-releases) releases page for that software.
  2. Update the [test server release notes](https://docs.cacophony.org.nz/admin/pages/home/release-notes-2), using the output from find-unreleased as a starting point.  
  3. Once the release is built, SSH into the appropriate test server.  Download the package and then install it
     * wget <url>
     * sudo dpkg -i <package.deb>
  5. Check the [integration tests](https://github.com/TheCacophonyProject/integration-tests) pass.  The tests run a series of functional checks against the browse portal, API server and thermal camera software.
     * Go to [travis](https://travis-ci.com/TheCacophonyProject/integration-tests/) and click restart
     * Check that the tests pass.
 
### Raspberry Pi Packages
Updates to our Raspberry Pi software is managed through Salt. Any configuration in the saltops test branch is automatically deployed to specified test devices. Similarly any configuration merged into the prod branch is automatically deployed onto all non-test devices.

The dev branch contains changes that are due to be merged into test. They are not automatically deployed.

1.  On the Salt master server (or locally if you have ops-tools), run find-unreleased.
2.  For each Raspberry Pi package that has unreleased changes:
  1. [Create a release in Github](/home/creating-releases) releases page for that software.
  2. Update the [test server release notes](https://docs.cacophony.org.nz/admin/pages/home/release-notes-2) using the nice goreleaser release notes, or output from find-unreleased as a starting point.
3.  Create a PR for the saltops dev branch which bumps the version that Salt will deploy to test devices for each changed package.  
4.  Merge the saltops dev branch (including the changes you've just made) into the test branch.   This will cause the software to be updated on test devices.  

### Test the test server updates
As soon as possible after the update is finished, check (or get someone else to) that the server and a test thermal camera is working as expected.
1.  Check the thermal camera has updated and has the expected version of all the packages.  
2.  Check each change is working as expected.   This means checking the new functionality is working as well as existing functionality in the same area that could be touched by the change. 

    
The steps are:
git fetch origin
git checkout -b update-test -t origin/test
git merge origin/dev
(review changes)
git push 
Create PR for the branch you've just pushed, get someone to review, then merge.
Update the release notes on docs.cacophony.org.nz as described at the top of this document.

    
    
##   Promote from test to prod
Connect to the salt server
Run: sudo find-server-upgrades
For each package that needs upgrading:
Review the actual changes involved (by consulting the release notes)
Confirm the changes are ok to go to prod 
Find evidence in the test environment
Talk to the responsible developer
SSH to the server(s) where the software runs
server-prod-api
server-prod-processing / server-prod-processing02
Get the package URL from the Github release page
wget <url>
sudo dpkg -i <package.deb>
Update the release notes on docs.cacophony.org.nz as described at the top of this document.

#### Promoting from test to prod
Start by promoting any changes from test to prod.

If you haven't already, clone the saltops repo
Pull the latest changes from all upstream branches: git fetch origin
Review the new changes in test
git log --reverse origin/prod..origin/test
For each change confirm on a test device that the change has been working ok. Asking the developer responsible for the work to do this is encouraged.
Be aware that some changes also require a change to top.sls in the master branch. This should be mentioned in the 
Once you are happy with these changes to to production, merge them into prod:
git checkout -b update-prod -t origin/prod
git merge origin/test
git push 
Create a PR for the branch you've just pushed, get someone to review, then merge.
Update the release notes on docs.cacophony.org.nz.

    
    
## Release Notes
The instructions above mention updates to the release notes. The details for how they work are as follows:
1.  The release notes are documented at https://docs.cacophony.org.nz/. 
2.  There's an two articles for each year. One for test and one for production.  
3.  Note that changes to software which runs on the thermal camera (e.g. thermal-recorder and audiobait) are grouped together under a single Thermal Camera heading. The audience for the release notes are end users and splitting these out according to software repository will be confusing.