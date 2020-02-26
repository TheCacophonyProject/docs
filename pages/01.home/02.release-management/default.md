---
title: 'Release Management'
---

This document describes the weekly process of promoting software from development -> test ->  production.  It is only of interest to the core team or anyone wanting to maintain their own cacophony server.  

Before starting the process make sure the previous release in test has been pushed to production. 

This document is written to be followed from top to bottom each release day.

## Server Packages
Start by upgrading and releasing our software that runs on our servers.

### Release new software to test
1. Run the find-unreleased tool on the Salt server (this can also be run locally if you have ops-tools). This will highlight any of Cacophony Project software with changes that haven't made it into a release yet.
2. For each server package that has unreleased changes:
  1. Create a release via the Github releases page for that software.
  2. Fill in the release notes, using the output from find-unreleased as a starting point.
  3. Once the release is built, SSH into the appropriate test server and install using wget and dpkg as above.
  4. Update the release notes on docs.cacophony.org.nz as described at the top of this document.
  5. Once all updated server packages have been deployed to the test servers you should run the integration tests and ensure they still pass. The tests run a series of functional checks against the browse portal, API server and thermal camera software.
Visit https://travis-ci.com/TheCacophonyProject/integration-tests/ in your web browser
Click the Restart Build button on the right hand side
Wait for the tests to run and ensure that they pass.
Raspberry Pi Packages
Updates to our Raspberry Pi software is managed through Salt. Any configuration in the saltops test branch is automatically deployed to specified test devices. Similarly any configuration merged into the prod branch is automatically deployed onto all non-test devices.

The dev branch contains changes that are due to be merged into test. They are not automatically deployed.
Promoting from test to prod
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
Unreleased changes
Next, create new packages for any Raspberry Pi related software which has unreleased changes.
On the Salt master server (this can also be run locally if you have ops-tools), run find-unreleased again.
For each Raspberry Pi package that has unreleased changes:
Create a release via the Github releases page for that software.
Our Go software will be built using Goreleaser which automatically creates nice release notes so there's no need to write them yourself for these repos.
For anything else, write your own release notes, using the output from find-unreleased as a starting point.
Once the release is built
Create a PR for the saltops dev branch which bumps the version that Salt will deploy to include the new version.
You may want to combine all the updates for the week into one PR to save time.


Merge dev to test
Finally, merge the saltops dev branch into the test branch. This will cause any updates that have been merged into dev over the past week (including what you may have done in the previous step) to be released to test devices.

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
    
    
    ## Release Notes
The instructions below mention updates to the release notes. The details for how they work are as follows:
The release notes are documented at https://docs.cacophony.org.nz/. 
There's an article for each year. For example: https://docs.cacophony.org.nz/home/release-notes-2020
There's a section for each week which includes everything that was released during that week.
Within each week there's a subsection of Production and Testing to show what was released to production and test.
The admin interface which supports editing of the docs pages is accessed at docs.cacophony.org.nz/admin
It is also possible to edit docs pages, including the release notes, by committing to the master branch at https://github.com/TheCacophonyProject/docs. Changes pushed to the master branch should appear on the site within a few minutes.
Note that changes to software which runs on the thermal camera (e.g. thermal-recorder and audiobait) are grouped together under a single Thermal Camera heading. The audience for the release notes are end users and splitting these out according to software repository will be confusing.