# <PROJECT_NAME>

A little info about your project and/ or overview that explains **what** the project is about. 

> Don’t get lazy just because this is for developers

- [Motivation](#motivation)
- [Build Status](#build-status)
- [Before You Begin](#before-you-begin)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Troubleshooting & FAQ](#troubleshooting-&-faq)
    - [Can't Stop all Docker Containers](#cant-stop-all-docker-containers)

## Motivation 

A short description of the motivation behind the creation and maintenance of the project and **why** the it exists

## Build Status
Build status of continus integration if applicable i.e. travis, appveyor etc. Ex. - 

![](https://img.shields.io/badge/Badges-if%20applicable-success)
![](https://img.shields.io/badge/Badges-if%20applicable-critical)
![](https://img.shields.io/badge/Tests-passing-32C955?logo=github&style=flat)
![](https://img.shields.io/badge/Gem-v0.0.1-success?logo=rubygems&style=flat)
![](https://img.shields.io/badge/My%20lib%20name-v0.0.1-success?logo=npm&style=flat)

## Before You Begin

You can list here all topics that the developers may need to know about before getting deep into this project, like recommendations about the basic building blocks that assemble this project. Ex. - 

- **MongoDB** - Go through [MongoDB Official Website](http://mongodb.org/) and proceed to their [Official Manual](http://docs.mongodb.org/manual/), which should help you understand NoSQL and MongoDB better.
- **Node.js** - Start by going through [Node.js Official Website](http://nodejs.org/) and this [StackOverflow Thread](http://stackoverflow.com/questions/2353818/how-do-i-get-started-with-node-js), which should get you going with the Node.js platform in no time.

## Prerequisites

A description of all prerequisites, knowledge or tools that anyone who wants to use the project might need before they begin. For example, if it runs on the latest version of Python, tell them to install Python. Make use of appropriate markdown styles to represente command line, code, etc. **Here's an example**:

- **Git** - [Download & Install Git](https://git-scm.com/downloads). OSX and Linux machines typically have this already installed.

- **Yarn** - You're going to use the [Yarn Package Manager](https://yarnpkg.com/) to manage your front-end packages. Make sure you've installed Node.js and npm first, then install bower globally using npm:

    ```bash
    $ npm install -g yarn
    ```

## Installation

The installation section shall make it clear how to install the project. However, if the steps to install the project follow any other commonly used steps, don't reinvent the wheel — simply provide a link and explain in detail any steps that may diverge from these steps. Ex. - 

To install **<PROJECT_NAME>**, follow these steps:

```bash
$ cd ../lorem
$ npm install
$ npm start
```

## Configuration

The configuration section is necessary even when little configuration is required. Use this section to list special notes about the configuration of this project. Ex. - 

To configure **<PROJECT_NAME>**, follow these steps:

1. Set max pool connection in the `connection.js` config file:

    ```js
    module.exports = [{
        name: 'myConnectionPool',
        host: 'hostname',
        port: 6379,
        poolSize: 200,
    }]
    ```

## Troubleshooting & FAQ

These sections are optional. If present, they should address questions that are asked frequently (this will save you time in the future). Outline common problems that developers encounter along with solutions (links are okay if the steps are long, but it is often helpful to provide a summary since links sometimes go stale). Ex. -

### Can't Stop all Docker Containers

When attempting to stop docker containers if you are getting the error:

```
ERROR: error while removing network: network compose_default id <compose_default id> has active endpoints
```

1. Use the command:

    ```bash
    $ docker network inspect compose_default
    ```

    This will display the compose `default_file`. It will have a connections section with containers referenced in it.

2. Use the command:

    ```bash
    $ docker network disconnect --force compose_default <container name>
    ```

    on any containers in the `compose_default` file. You should then be able to stop and start the rewind app normally now.