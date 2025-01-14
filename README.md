# IBM PAIRS Geoscope open source modules

[![Build Status](https://travis-ci.org/IBM/ibmpairs.svg?branch=master)](https://travis-ci.org/IBM/ibmpairs)

This repository provides an interface to the geo-spatial big data platform
[IBM PAIRS Geoscope](https://ibmpairs.mybluemix.net).

E.g. the module in the subdirectory `paw` serves as a wrapper employing the IBM PAIRS
core RESTful API served through the host reachable via
[https://pairs.res.ibm.com](https://pairs.res.ibm.com/manual/api-doc/) to load data into (native)
Python data structures.


# General Notes

If you like to contribute, please read [CONTRIBUTING.md](CONTRIBUTING.md) first.
A list of maintainers is recorded in [MAINTAINERS.md](MAINTAINERS.md).


# Installation and Usage

If you have installed the Python package manager [PIP](https://github.com/pypa/pip),
simply run
```Bash
pip install git+https://github.com/ibm/ibmpairs
```
Then you import the IBM PAIRS API wrapper via:
```Python
from ibmpairs import paw
```

# Getting started

Simply get your feet wet with the [tutorial](tutorials/IBM-PAIRS-API-wrapper-tutorial.ipynb).
The full API documentation you can generate by running
```Bash
cd docs && make html
```
to open `docs/_build/html/index.html` with your favorite browser, provided you
have installed [Sphinx](https://www.sphinx-doc.org/) and the corresponding
[ReadTheDocs](https://readthedocs.org/) theme by running e.g.
```Bash
pip install sphinx sphinx_rtd_theme
```


# Running in a Docker container

A self-contained environment can be built with [Docker](http://www.docker.com) using
```Bash
git clone https://github.com/ibm/ibmpairs
cd ibmpairs
docker build -t ibmpairs .
```
and launched via
```Bash
docker run \
    -dit \
    -p 18380:18380 \
    --name ibmpairs \
    ibmpairs:latest
```
or, instead of the above, simply `docker-compose up ibmpairs` such that you can type
into your browser
```
http://localhost:18380
```
