# A Node.js Express / Redis Stack template on Gitpod

This is a [Node.js](https://nodejs.org/) [Express](http://expressjs.com/) template configured for ephemeral development environments on [Gitpod](https://www.gitpod.io/) with [Redis Stack](https://redis.io/docs/stack/) using the [node-redis](https://github.com/redis/node-redis) client and [RedisInsight](https://github.com/RedisInsight/RedisInsight) visualization tool.  You can also run this application locally if you prefer.

The application is a basic counter that stores a value in Redis in the `mycounter` key.  It's intended as a start point for building your own Express applications that use Redis.

If you prefer to work with Python, we've also built this same application using Python and the Flask framework.  [Check it out here](https://github.com/simonprickett/gitpod-flask-redis).

## Quick Start

There are two ways of running this application - entirely in the cloud with Gitpod, or locally on your own machine either with your own install of Redis Stack or using Docker.

### Using Gitpod

When using Gitpod, the only things you need are:

* A modern browser (we have tested with [Google Chrome](https://www.google.com/chrome/)).
* A [GitHub](https://github.com) account.

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

* The [git command line tools](https://git-scm.com/downloads).
* A recent version of [Node.js](https://nodejs.org/) (use the current LTS / Long Term Stable version where possible).  The application has been tested on Node v16.4.2.
* [Docker Desktop](https://www.docker.com/products/docker-desktop/) (to run a Redis Stack container) or a local install of Redis Stack ([installation options here](https://redis.io/docs/stack/get-started/install/)).
* Your favorite IDE if you want to edit / read the code (we like [VS Code](https://code.visualstudio.com/)).

First, clone the repo and install dependencies:

```bash
$ git clone https://github.com/simonprickett/gitpod-flask-redis.git
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

Before diving into code, let's first try out the application and see what data is stored in Redis.

* Initially, there's nothing in Redis and the application shows the counter's value to be 0.
* Pressing the "Increment" button adds one to the counter's current value, which is stored in a key named "mycounter" in Redis.
* Press "Increment" a few times, then refresh your RedisInsight tab's view of the database to see that a key named "mycounter" has been added, and that it's value matches that shown in the application front end.
* Press the "Reset" button, then refresh your RedisInsight tab's view of the database.  Note that the "mycounter" key has now been deleted.

### Front End

The application's front end isn't our focus here.  It's a simple web application built with Bulma and vanilla JavaScript.  The JavaScript that handles button presses is contained in `static/app.js` and the HTML can be found in `views/homepage.ejs` - it's a simple [EJS template](https://simonprickett-gitpodexpr-eamwc2bab7h.ws-eu38.gitpod.io/).  There are no CSS files in this repo, the CSS and Font Awesome JS files that Bulma uses are served from a CDN.

### Back End

Now let's look at the code in `app.js` to see how to use Node Redis to connect to Redis Stack.

TODO

## What Capabilities does Redis Stack have?

TODO

## Additional Resources

Looking to learn more about Redis? Here's some useful resources:

* Chat with us and get your questions answered on the [Redis Discord server](https://discord.gg/redis).
* Subscribe to our [YouTube channel](https://www.youtube.com/c/Redisinc).
* [redis.io](https://redis.io/) - Docmentation and reference materials.
* [developer.redis.com](https://developer.redis.com) - the official Redis Developer Site.
* [Redis University](https://university.redis.com) - free online Redis courses.