# iojs-install-script

A script to install basic development tools for io.js - the new node.js - git, iojs, gcc, pkg-config, etc

* [Instructions for OS X](#apple-os-x)
* [Instructions for Ubuntu Linux](#ubuntu-linux)
* [Instructions for TL;DR](#tldr)
* [Important Notes](#other-things-you-should-know)

## Screencast

[How to Setup a VPS for io.js Development](https://www.youtube.com/watch?v=ypjzi1axH2A) - [(3:06 installing io.js](https://www.youtube.com/watch?v=ypjzi1axH2A#t=186))

## TL;DR

If you kinda know what you're doing already:

```bash
echo "v1.0.1" > /tmp/IOJS_VER
curl -fsSL bit.ly/iojs-dev -o /tmp/iojs-dev.sh; bash /tmp/iojs-dev.sh
```

Or, if you don't need any developer tools and you *just* want io.js

```bash
# Or if you don't need any development tools
echo "v1.0.1" > /tmp/IOJS_VER
curl -fsSL bit.ly/iojs-min | bash
```

## Apple OS X

First you need to **Install XCode Command Line Tools**

```bash
xcode-select --install
```

Then you need to **Accept the XCode License** by running any command installed by Xcode with sudo. We'll use git.

```bash
sudo git --version
```

You can scroll to the bottom by hitting shift+G (capital G).

Type `agree` and hit enter to accept the license.

Now you can install io.js (the new node.js)

```bash
# Specify the version of iojs to install
echo "v1.0.1" > /tmp/IOJS_VER

# And install away!
curl -fsSL bit.ly/iojs-dev -o /tmp/iojs-dev.sh; bash /tmp/iojs-dev.sh
```

*TODO*: Make it easier to accepting the license (automatic?)

## Ubuntu Linux

```bash
# Specify the version of iojs to install
echo "v1.0.1" > /tmp/IOJS_VER

# And install away!
wget -nv bit.ly/iojs-dev -O /tmp/iojs-dev.sh; bash /tmp/iojs-dev.sh
```

## Other things you should know

**NOTE**: If you have node installed, this script will rename it so that it isn't overwritten by the iojs installer.

This is what gets installed:

* rsync
* curl
* wget
* git
* xcode / brew / build-essential / pkg-config / gcc
* iojs (including npm and node symlink)
* jshint

**NOTE**: If `fail2ban` is not already securing ssh, you will be asked to install it.


Front-End Extras
================

These are **not installed**, but you may wish to use them if you're doing front-end work as well

* bower
* uglifyjs
* yo
* jade
* less
