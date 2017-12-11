# Scibian.org website

## Overview

This repository contains the source files Scibian.org website:
https://scibian.org

The website is static and the pages are generated using the
[Hyde templating engine](http://hyde.github.io/).

## Development

To install a development environment on a Scibian 8 workstation, run the following
commands:

```
$ sudo apt-get install python-pip virtualenv
$ virtualenv $HOME/.virtualenv
$ . $HOME/.virtualenv/bin/activate
$ pip install hyde
```

It sequentially does the following things:

1. install pip and virtualenv utilities
2. create a virtualenv in your home directoy
3. enable the virtualenv
4. install hyde in your home

Once the development environment is installed, only step 3. is needed to setup
the environment in a shell.

Then, in the root directory of this source code, run:

```
$ rm -rf deploy && hyde gen && hyde serve
```

This will basically generate the HTML pages and launch a local HTTP server to
serve the website. NB: the `hyde serve` command can run in background in another
shell during development iterations.

Then, connect to the following URL within your browser: http://localhost:8080/

## Deployment

Before deploying website updates on the production environment, one must test
the updates in the pre-production environment before. In order to update the
pre-production environment with last commits to this repository, connect to
scibian.org server through SSH and run the following commands:

```
# cd /local00/scibian.org
# git pull github
# . env/bin/activate
# hyde gen -c preprod.yaml
```

Then, check of the pre-production website: https://scibian.org/preprod-site/

If everything is OK, run the following command to update production website:

```
# hyde gen -c prod.yaml
```

Finally, check of the production website: https://scibian.org/
