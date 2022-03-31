# A Node.js Express / Redis Stack template on Gitpod

This is a [Node.js](https://nodejs.org/) [Express](http://expressjs.com/) template configured for ephemeral development environments on [Gitpod](https://www.gitpod.io/) with [Redis Stack](https://redis.io/docs/stack/) using the [node-redis](https://github.com/redis/node-redis) client and RedisInsight visualization tool.  You can also run this application locally if you prefer.

The application is a basic counter that stores a value in Redis in the `mycounter` key.  It's intended as a start point for building your own Express applications that use Redis.

## Quick Start

There are two ways of running this application - entirely in the cloud with Gitpod, or locally on your own machine either with your own install of Redis Stack or using Docker.

### Using Gitpod

When using Gitpod, the only things you need are:

* A modern browser (we have tested with Google Chrome).
* A GitHub account.

Click the button below to start a new cloud development environment using Gitpod:

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/simonprickett/gitpod-express-redis)

If you're using Gitpod for the first time, you'll need to authorize it to work with your GitHub account.

Gitpod will then open a workspace in the browser for you.  This contains:

* VS Code for editing the code.
* An embedded browser window with the application running in it.
* Two terminal sessions: the left hand terminal can be used for entering commands, the right hand one starts the application for you using nodemon.  nodemon restarts the application for you whenever you save code changes in VS Code.

Take a note of your workspace URL which looks something like this:

```
https://yourgithubusername-gitpodexpr-eamwc2bab7h.ws-eu38.gitpod.io/
```

If you want to open the application in a separate browser tab outside of the Gitpod workspace tab, append `5000-` to the workspace URL, for example:

```
https://5000-yourgithubusername-gitpodexpr-eamwc2bab7h.ws-eu38.gitpod.io/
```

To start RedisInsight, append `8001-` to the workspace URL and open that in another new tab.  For example:

```
https://8001-yourgithubusername-gitpodexpr-eamwc2bab7h.ws-eu38.gitpod.io/
```

You'll need to agree to the terms and conditions the first time that you start RedisInsight.

The application should show that the current value of the counter is 0, and RedisInsight should show you an empty database with no keys yet.

### Running Locally

To run the application locally you'll need to install the following:

* The git command line tools.
* A recent version of Node.js (use the current LTS / Long Term Stable version where possible).  The application has been tested on Node v16.4.2.
* Docker Desktop (to run a Redis Stack container) or a local install of Redis Stack.
* Your favorite IDE if you want to edit / read the code.

First, clone the repo and install dependencies:

```bash
$ git clone TODO.git
$ cd gitpod-express-redis
$ npm install
```

If you're using Docker to run Redis Stack, start the container:

```bash
$ docker-compose up -d
```

This starts a Redis Stack container with Redis listening on port 6379 and RedisInsight listening on port 8001.

If you're not using Docker, install a copy of Redis Stack using your platform's package manager (see options here).  Make sure it's up and running with Redis on port 6379 and RedisInsighg on port 8001 (these are the default port values).

Once Redis Stack is up and running, you can go ahead and start the application like this:

```bash
$ npm run dev
```

This starts the application using nodemon.  nodemon restarts the application for you whenever you save code changes from your IDE.

Now, open tabs in your browser for each of the following URLs:

* Application: http://127.0.0.1:5000
* RedisInsight: http://127.0.0.1:8001 (agree to the terms and conditions the first time you visit this URL)

The application should show that the current value of the counter is 0, and RedisInsight should show you an empty database with no keys yet.

Don't stop the application now, but when you're ready to, press Ctrl-C in the terminal window that npm is running in.

If you're using Docker, you can stop the Redis Stack container like this when you're finished with it:

```bash
$ cd gitpod-express-redis
$ docker-compose down
```

## How the Application Works

TODO

## What's in Redis Stack?

TODO



