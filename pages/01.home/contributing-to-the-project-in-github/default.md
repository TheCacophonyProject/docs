---
title: 'Contributing to the project in GitHub'
published: true
publish_date: '07-01-2020 18:09'
taxonomy:
    category:
        - Developer
---

All contributions to code for The Cacophony Project should be committed using the Fork and Pull mechanism in GitHub. 

The basic work flow is:
1. Fork a GitHub repository.
2. Clone the forked repository to your local system.  _(You can easily do this through the GitHub interface)_
3. Add a the original Cacophony repository as a Git remote. _(See below for how to do this)_
4. Create a feature branch in which to place your changes.
5. Make your changes to the new branch.
6. Commit the changes to the branch.
7. Push the branch to GitHub.
8. Open a pull request from the new branch to the original repo.
9. On the pull page check that **All checks have passed**.  _(This is when we get run our style checker and tests)_
10. Wait for a project maintainer to approve your code.
11. Clean up your code after your pull request is merged.

Extensive details on how to do this can be found in Scott Lowe's article [Using the Fork and Branch GitHub workflow](https://blog.scottlowe.org/2015/01/27/using-fork-branch-git-workflow/).   

## How to add the original (upstream) repository to your repository
Add our Cacophony repository remote to your repository by calling:
```console
> git remote add upstream https://github.com/TheCacophonyProject/<project>.git
```
This allows you to get the latest code and use it to update your fork at anytime by calling:
```console
> git pull upstream master
> git push origin master
```