---
title: 'Projects for open source'
---

# So you want to help us?.  Awesome!  

We  <b style='color:darkred'>love</b> people like you. 

For a start, to get things rolling you might like to try one of our [good first issues](https://github.com/search?utf8=%E2%9C%93&q=org%3ATheCacophonyProject+is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22&type=Issues)

If you are looking for something a bit more <b style='color:navy'>chunky</b> then have a look at our mini- or mega-projects below.   This is a list of things we would <b style='color:darkred'>really love</b> to see happen, but haven't managed to make happen yet...    Complete one of these and you'll know you've <b style='color:navy'>made your mark</b>, <b style='color:forestgreen'>helped the birds</b> and shown the world the kind of <b style='color:black'>code-ninjaring</b> that you are capable of. 

### Mini project - password reset for the browse portal
**why? ** Because, right now someone has to personally reset forgotten passwords and not everyone remembers the zillionth login!.  

**tools?** <b style='background-color:GreenYellow'>vuejs</b>  [browse](https://github.com/TheCacophonyProject/cacophony-browes), <b style='background-color:GreenYellow'>nodejs</b>  [api](https://github.com/TheCacophonyProject/cacophony-api),
___

### Mega project - rewrite API tests in JS, maybe using Cypress
**why?**  The api and browse are written in nodejs, the api-tests in python, and the browse integration tests in Cypress (js).   If everything was js and no python involved it would be easier for people to contribute and to maintain. 

**tech?** Reading <b style='background-color:GreenYellow'>python</b>, writing <b style='background-color:GreenYellow'>node.js</b>, [api](https://github.com/TheCacophonyProject/cacophony-api), also consider the relationship with our [cypress browse-api integration tests](https://github.com/TheCacophonyProject/integration-tests)

___

### Mega Mega project:  Automate testing for our data collector sidekick (android)
Our sidekick app connects to our raspberry pi thermal camera via wifi to get recordings off devices in the field that are outside cell phone range.   Since this is a workflow that will happen in the field, it is vital that it works first time, everytime so we need some tests. 

### Mega-step:  Get sidekick running in a container (preferably docker)
**why?**  We already have the thermal camera running in a docker image on linux.   So if we could get this step up and running we could start writing some tests. 

**tech?**  <b style='background-color:GreenYellow'>Android</b>,<b style='background-color:GreenYellow'>Docker</b>, [Cacophony sidekick](https://github.com/TheCacophonyProject/sidekick)


 