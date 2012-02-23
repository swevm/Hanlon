# Project Razor

## Introduction

Project Razor is a power control, provisioning, and management application designed
to deploy both bare-metal and virtual compute resources with tight integration to
DevOps-style tool sets.

## Authors

[Nicholas Weaver](https://github.com/lynxbat)
[Tom McSweeney](https://github.com/tjmcs)

## Installation

### Node.js:
[Node.js install with package manager](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager)
[Node Package Manager(NPM)](http://npmjs.org/)
[Express install via NPM](http://expressjs.com/guide.html)

### Database

#### Mongo

_todo_

## Prereqs

* Ruby >= 1.9.3
* Assorted gems - see (Gemfile)
* Node.js >= 0.6.10
* Node.js Express package
 

## Environment Variables
* $RAZOR_HOME
    >Root directory for Razor install

* $RAZOR_RSPEC_WEBPATH
    >Root directory for dropping RSpec html _(optional)_

* $RAZOR_LOG_PATH
>Path for razor logs _(optional)_l
>>Default = $RAZOR_HOME/log

* $RAZOR_LOG_LEVEL
    > Verbosity for logs _(optional)_
    >> 0 = Debug
    >> 1 = Info
    >> 2 = Warn
    >> 3 = Error (default)
    >> 4 = Fatal
    >> 5 = Unknown


## Directory structure
    ./bin - control scripts
    ./conf - configuration YAML files
    ./doc - Documentation (YARD)
    ./images - default images directory
    ./install - installation bits
    ./lib - root library folder
    ./test_scripts - testing scripts
    ./rspec - unit tests (RSpec)

## Starting services

Start Razor API with:

    cd $RAZOR_HOME/bin/node
    node razor.js


## Notes

Use the newest mongo ruby driver build as there is a bug with connect_timeout scoping error
that hasn't been merged into available gem yet

The fix below is assuming RVM as Ruby environment manager. If using global RVM gems make sure
and 'rvm use ruby-1.9.3@global' before installing updated mongo driver.

    wget https://github.com/mongodb/mongo-ruby-driver/zipball/master
    unzip master
    cd mongodb-mongo-ruby-driver-99d9dfd/
    gem build mongo.gemspec
    gem install mongo-1.5.2.gem