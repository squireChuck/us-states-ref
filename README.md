# us-states-ref
## Intro
Quick reference of info related to U.S. states, e.g. sample addresses, driver's license formats, etc. 

Exposes service for use in code, Express router for convenient GET endpoints, e.g. to hit with your testing scripts/other personal work.

## Pre-req's
Node 4.6.0

## Setup
1. Copy or clone project to computer.

2. Install the dependencies listed in package.json, e.g. in the command prompt, nav to the us-states-ref folder and `npm install`

3. After that's done, stay in the same folder and run `jasmine`. If the tests pass, you're all set!

4. See the apiController for mountable endpoints on an Express app.

## Example usage
### Using the service in code
```javascript
var StateService = require('../services/StateService');
var stateService = new StateService();
console.log(stateService.getAllStates());
```

### Mounting endpoints to an existing Express app
```javascript
var express = require('express');
var apiController = require('us-states-ref').usStatesExpressRouter;

// app.use(rootPath, expressRouter)
app.use('/usstates', apiController)
```
Test with a GET request to /usstates/api/v1/states

### Endpoint client
See an example at [us-states-ref-client](https://github.com/squireChuck/us-states-ref-client).

## Notes for users
Drivers license format source - the Internet... your mileage may vary.

## Wishlist
1. Sample addresses for all states, which will pass the remaining failing jasmine specs.

2. Extra endpoints for finer grained data - see apiController for ideas. 

3. Get random sample addresses from an external source?

## Project 20/20
1. The Express router makes it trivial to add endpoints onto an existing Express app. Some similarity to EARs/WARs on a Java web server.

2. Jasmine is easy to pick up, many concepts also transferable from JUnit/Spock. Simple enough to set up test cases running through data-driven scenarios.

3. Publishing packages to npm and using them in different projects (via inclusion in a package.json) is a smooth process. These service + Express router packages might be handy for a Node/Express microservices server. Time'll tell... 

4. Node's require can read in a json file and transform for js objects. Painless but be aware - it's a synchronous/blocking operation.
