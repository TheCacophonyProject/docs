---
title: 'Projects for open source'
---

# So you want to help us?.  Awesome!  

We  <b style='color:red'>love</b> love people like you. 

For a start, to get things rolling you might like to try one of our [good first issues](https://github.com/search?utf8=%E2%9C%93&q=org%3ATheCacophonyProject+is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22&type=Issues)

If you are looking for something a bit more chunky then have a look at our mini- or mega-projects below.   This is a list of things we would really love to see happen, but just have managed to make happen yet.   Then you can sign your name to a piece of functionality and know you've made your mark, helped the birds and shown the world the kind of code-ninjaring that you are capable of.   Need more inspirations?  Read 

### Mini project - password reset for the browse portal
**why? ** Because, right now someone has to personally reset passwords.   And lets face it how many people remember every password now we have like a zillion of logins.  

**tools?** vue, js (cacophony-browse), node.js (cacophony-api)
___

### Mega project - rewrite API tests in JS, maybe using Cypress
**why?**  The api and browse are written in nodejs, the api-tests in python, and the browse integration tests in Cypress (js).   If everything was js and no python involved it would be easier for people to contribute and to maintain. 

**tech?** Reading python, writing node.js, [api](https://github.com/TheCacophonyProject/cacophony-api), also consider the relationship with our [cypress browse-api integration tests](https://github.com/TheCacophonyProject/integration-tests)

___

### Mega Mega project:  Automate testing for our data collector sidekick (android)
Our sidekick app connects to our raspberry pi thermal camera via wifi to get recordings off devices in the field that are outside cell phone range.   Since this is a workflow that will happen in the field, it is vital that it works first time, everytime so we need some tests. 

#### Mega-step:  Get sidekick running in a container (preferably docker)
**why?**  We already have the thermal camera running in a docker image on linux.   So if we could get this step up and running we could start writing some tests. 

**tech?**  Android, Docker, [Cacophony sidekick](https://github.com/TheCacophonyProject/sidekick)


 