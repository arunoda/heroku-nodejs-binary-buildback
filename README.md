Heroku Buildpack for NodeJS (using official binaries)
=====================================================

* This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for Node.js apps.
* It uses binaries from nodejs.org and you are up to date always

Default NodeJS version: 0.10.0

Usage
-----

#For a new app

    $ heroku create --buildpack https://github.com/arunoda/heroku-nodejs-binary-buildback.git
    $ git push heroku master

#For an existing app

    $ heroku config:add BUILDPACK_URL=https://github.com/arunoda/heroku-nodejs-binary-buildback.git
    $ git push heroku master

Using Custom NodeJS version
---------------------------

**Only for versions >= 0.8.x**

    $ heroku labs:enable user-env-compile -a <app_name> #one time action
    $ heroku config:add NODE_VERSION=<node_version>

Using Alternate package.json
--------------------------
For a large scale app, we might have to deal with several heroku apps. Specially in case where we need to fire more than 1 web processes in a single app. 

For those situations, we need to use separate package.json files. This is how we can do with this buildpack.

    $ heroku labs:enable user-env-compile -a <app_name>
    $ heroku config:add ALTERNATE_PACKAGE_JSON=your-alternate-package.json
