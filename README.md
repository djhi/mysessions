MySessions
=========================

This is an umbrella repository for the MySessions applications.

## Initialization
* If you haven't cloned this repository yet, use this command to clone it with its submodules
```
git clone --recursive https://github.com/djhi/mysessions.git
```

* If you haven't cloned this repository with submodules, you must
initialize them:
```
git submodule init --recursive
git submodule update --recursive
```

* If you want to run the tests, you need a running selenium server. You can install one easily by using the [selenium-standalone](https://www.npmjs.com/package/selenium-standalone) NPM package.
```
npm i -g selenium-standalone
```
*you might have to run this command as root*

## Structure
There are 4 folders in this repository:
### config

Contains settings files for our environnements (development, production).

### mysessions-core

This is a **Meteor package** containing code common to the mobile and web applications (collections, workflows, etc.)

It can be tested independently by using the [practicalmeteor-spacejam](https://github.com/practicalmeteor/spacejam/) NPM package.

*Velocity does not support packages tests yet. Once it will, I'll convert those tests to use the most appropriate testing framework with Velocity for it (probably `cucumber`, maybe `jasmine`).*

### mysessions-web

This is the **Meteor application** for the Web UI. It uses `mysessions-core`.

It uses [meteor:velocity](http://velocity.meteor.com) with [xolvio:cucumber](https://github.com/xolvio/meteor-cucumber) to run the tests in parallel.

### mysessions-mobile

This WILL BE the **Meteor application** for the Mobile UI. It uses `mysessions-core`.

It uses [meteor:velocity](http://velocity.meteor.com) with [xolvio:cucumber](https://github.com/xolvio/meteor-cucumber) to run the tests in parallel.

## Scripts
2 scripts are supplied to ease starting the applications and tests:

* `selenium`: used to start a selenium server installed by the [selenium-standalone](https://www.npmjs.com/package/selenium-standalone) NPM package

* `start`: used to start the meteor Web application

*Another script will be supplied to start the mobile application.*
