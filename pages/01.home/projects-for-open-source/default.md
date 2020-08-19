---
title: 'Projects for open source'
---

# So you want to help us?.  Awesome!  

We  <b style='color:darkred'>love</b> people like you. 

For a start, to get things rolling you might like to try one of our [good first issues](https://github.com/search?utf8=%E2%9C%93&q=org%3ATheCacophonyProject+is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22&type=Issues)

If you are looking for something a bit more <b style='color:navy'>chunky</b> then have a look at our mini- or mega-projects below.   This is a list of things we would <b style='color:darkred'>really love</b> to see happen, but haven't managed to make happen yet...    Complete one of these and you'll know you've <b style='color:navy'>made your mark</b>, <b style='color:forestgreen'>helped the birds</b> and shown the world the kind of <b style='color:black'>code-ninjaring</b> that you are capable of. 

Before you start any of these, it's probably worth getting in touch with us so we can give you the background  and get you started right. 
___

###  Project - Password reset for the browse portal
**why?** Because, right now someone has to personally reset forgotten passwords and not everyone remembers the zillionth login!.  

**tools?** <b style='background-color:GreenYellow'>vuejs</b>  [browse](https://github.com/TheCacophonyProject/cacophony-browse), <b style='background-color:GreenYellow'>nodejs</b>  [api](https://github.com/TheCacophonyProject/cacophony-api),
___

###  Project - Demo for interested parties and new contributors.
**why?** Right now it's hard to see what our  software does because you sign up and can't see any recording.   Then if you want to change code it's hard to know how to add videos to test with.   

**tools?** There are many parts to this one.   You could <b style='background-color:GreenYellow'>write documentation</b> or change the api to let everyone see recordings from certain groups (but not delete them) <b style='background-color:GreenYellow'>nodejs</b>  [api](https://github.com/TheCacophonyProject/cacophony-api), 


___

###  Project - Automated browse tests in Cypress.io
**why?**  So that when we make new releases we don't break existing functionality.  The test frame work is done but we need to test more of our features.

**tech?** <b style='background-color:GreenYellow'>js</b>, <b style='background-color:GreenYellow'>cypress.io</b>, [integration-tests](https://github.com/TheCacophonyProject/integration-tests) testing [browse portal](https://github.com/TheCacophonyProject/cacophony-browse)


___

###  Project - rewrite API tests in JS, maybe using Cypress
**why?**  The api and browse are written in nodejs, the api-tests in python, and the browse integration tests in Cypress (js).   If everything was js and no python involved it would be easier for people to contribute and to maintain. 

**tech?** Reading <b style='background-color:GreenYellow'>python</b>, writing <b style='background-color:GreenYellow'>node.js</b>, [api](https://github.com/TheCacophonyProject/cacophony-api), also consider the relationship with our [cypress browse-api integration tests](https://github.com/TheCacophonyProject/integration-tests)

___

###  Project - Port sound lure setup interface to Vuejs
**why?** When we moved over to our new <b style='background-color:GreenYellow'>vuejs</b> front-end the sound lure stuff had not been finished.   And it still isn't.   Once we move this over we will no longer need our extra old front end server which will help us heaps. 

**tech?** <b style='background-color:GreenYellow'>vuejs</b>, [browse](https://github.com/TheCacophonyProject/cacophony-browse), reading <b style='background-color:GreenYellow'>js</b>, [web-old](https://github.com/TheCacophonyProject/cacophony-web-old),  

___


### Mega project:  Automate testing for our data collector sidekick (android)
Our sidekick app connects to our raspberry pi thermal camera via wifi to get recordings off devices in the field that are outside cell phone range.   Since this is a workflow that will happen in the field, it is vital that it works first time, everytime so we need some tests. 

### Good step:  Get sidekick running in a container (preferably docker)
**why?**  We already have the thermal camera running in a docker image on linux.   So if we could get this step up and running we could start writing some tests. 

**tech?**  <b style='background-color:GreenYellow'>Android</b>,<b style='background-color:GreenYellow'>Docker</b>, [Cacophony sidekick](https://github.com/TheCacophonyProject/sidekick)


 