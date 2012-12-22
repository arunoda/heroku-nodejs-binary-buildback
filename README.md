Heroku Buildpack for NodeJS (using official binaries)
=====================================================

* This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for Node.js apps.
* It uses binaries from nodejs.org and you are up to date always
* This includes latest version of node-gyp(0.8.x) too 

Default NodeJS version: 0.8.16

Usage
-----

#For a new app

    $ heroku create --stack cedar --buildpack https://github.com/arunoda/heroku-nodejs-binary-buildback.git
    $ git push heroku master

#For a existing app

    $ heroku config:add BUILDPACK_URL=https://github.com/arunoda/heroku-nodejs-binary-buildback.git
    $ git push heroku master

Using Custom NodeJS version
---------------------------

**Only for versions >= 0.8.x**

    $ heroku labs:enable user-env-compile -a <app_name>
    $ heroku config:add NODE_VERSION=<node_version>
