# Heroku Buildpack for N|Solid

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

This is the official [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for [N|Solid](https://nodesource.com/products/nsolid) apps.

## Usage

Create a Node.js web app. [Nodejs Getting Started](https://github.com/heroku/node-js-getting-started) can be used as a sample starter.

```
$ heroku create
$ git push heroku master
$ heroku open
```

`$ heroku config:add BUILDPACK_URL=https://github.com/joemccann/nsolid-2.0-heroku-buildpack -a YOUR_APP_NAME`

Note: if you have an `app.json` file, like the one in the Getting Started repo, you'll need to remove the property and value `image: heroku/nodejs` to verify that the deployment fetches N|Solid and not the Heroku Node.js build.

You will have N|Solid 2.0 powering your Node app!

## Documentation

For more information about using this Node.js buildpack on Heroku, see these Dev Center articles:

- [Heroku Node.js Support](https://devcenter.heroku.com/articles/nodejs-support)
- [Getting Started with Node.js on Heroku](https://devcenter.heroku.com/articles/nodejs)

For more general information about buildpacks on Heroku:

- [Buildpacks](https://devcenter.heroku.com/articles/buildpacks)
- [Buildpack API](https://devcenter.heroku.com/articles/buildpack-api)


If you have trouble upgrading to the latest version of the buildpack, please
open a support ticket at [help.heroku.com](https://help.heroku.com/) so they can assist.


## Hacking

To make changes to this buildpack, fork it on GitHub.
Push up changes to your fork, then create a new Heroku app to test it,
or configure an existing app to use your buildpack:

```
# Create a new Heroku app that uses your buildpack
heroku create --buildpack <your-github-url>

# Configure an existing Heroku app to use your buildpack
heroku buildpacks:set <your-github-url>

# You can also use a git branch!
heroku buildpacks:set <your-github-url>#your-branch
```

## Tests

The buildpack tests use [Docker](https://www.docker.com/) to simulate
Heroku's Cedar and Cedar-14 containers.

To run the test suite:

```
make test
```

Or to just test in cedar or cedar-14:

```
make test-cedar-10
make test-cedar-14
```

The tests are run via the vendored
[shunit2](http://shunit2.googlecode.com/svn/trunk/source/2.1/doc/shunit2.html)
test framework.

