---
title: 'Creating Releases'
taxonomy:
    category:
        - Developer
    tag:
        - 'Core Team'
---

For most of the Cacophony Project's software, releases are created automatically by [Travis CI](https://travis-ci.com). In order to create a release:

- Click the word "Releases" on the code (main) page on the repository on Github (or add _\releases_ to the URL).
- Click Draft new Release.
- Enter a new version number.
  * remember that we use [Semantic Versioning](https://semver.org/)
  * Start the tag with a "v", for example `v1.2.3`.
- Ensure the correct revision is being tagged. It's often OK to just go with the current top of the `master` branch (the default) but if you want to be extra careful you can pick a specific revision.
- Click Publish.

This will create a Git tag for the release and cause Travis CI to run the tests for the tagged revision and generate a release. This typically results in a [Debian package](https://www.debian.org/doc/manuals/debian-faq/ch-pkg_basics) (.deb file) which is then attached to the release on Github. The package can then be installed from there.