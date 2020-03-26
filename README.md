Management of Python-related Docker images
==========================================

- [Overview](#overview)
  * [References](#references)
- [Projects this repository helps to manage](#projects-this-repository-helps-to-manage)
  * [Docker light (Alpine) images to support Machine Learning (ML) in Python](#docker-light--alpine--images-to-support-machine-learning--ml--in-python)
  * [Docker images to support development on C++ and Python stacks](#docker-images-to-support-development-on-c---and-python-stacks)
    + [General C++/Python development](#general-c---python-development)
    + [Python Machine Learning (ML)](#python-machine-learning--ml-)
  * [Python bindiings for OpenTravelData (OPTD)](#python-bindiings-for-opentraveldata--optd-)
  * [Python installation](#python-installation)
- [Procedures](#procedures)
  * [New Python stable version](#new-python-stable-version)
    + [Add the new Python version to the C++/Python Docker images](#add-the-new-python-version-to-the-c---python-docker-images)
    + [Update the Python environment of the Python Jupyter Docker image](#update-the-python-environment-of-the-python-jupyter-docker-image)
    + [Update the Python environment of the Python Alpine Docker image](#update-the-python-environment-of-the-python-alpine-docker-image)
    + [Non Docker projects to update](#non-docker-projects-to-update)
      - [Machine Learning (ML) induction](#machine-learning--ml--induction)
      - [Python bindings for OpenTravelData (OPTD)](#python-bindings-for-opentraveldata--optd-)
      - [Python bindings for OpenTREP](#python-bindings-for-opentrep)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


# Overview

## References
* [This GitHub repository - Docker Image Management](https://github.com/python-helpers/docker-image-management)

# Projects this repository helps to manage

## Docker light (Alpine) images to support Machine Learning (ML) in Python
* [ML Helpers GitHub repository](https://github.com/machine-learning-helpers/docker-python-alpine)
* [Docker land page for `artificialintelligence/python-alpine`](https://hub.docker.com/repository/docker/artificialintelligence/python-alpine)
  + [Docker image page for `artificialintelligence/python-alpine:alp311`](https://hub.docker.com/layers/artificialintelligence/python-alpine/alp311/images/sha256-ad89caf67586d26c9ee1f187bb781a63856c3c8ea8b20a7b0785d71170359091?context=repo)
* [Quay land page for `artificialintelligence/python-alpine`](https://quay.io/repository/artificialintelligence/python-alpine)
* Distributions: `alpine-3.11`, `py37-alp311`
* Badges:
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/artificialintelligence/python-alpine)](https://hub.docker.com/repository/docker/artificialintelligence/python-alpine/general)
[![Docker Repository on Quay](https://quay.io/repository/artificialintelligence/python-alpine/status "Docker Repository on Quay")](https://quay.io/repository/artificialintelligence/python-alpine)

## Docker images to support development on C++ and Python stacks

### General C++/Python development
* [GitHub repsitory - Docker for C++ development](https://github.com/cpp-projects-showcase/docker-images)
* [Docker land page for `cpppythondevelopment/base`](https://hub.docker.com/repository/docker/cpppythondevelopment/base)
  + [Docker image page for `cpppythondevelopment/base:ubuntu1804`](https://hub.docker.com/layers/cpppythondevelopment/base/ubuntu1804/images/sha256-d79bb20ef0ed2eb2e474ea06806b69ac95d36de6056ce9185eb9a904e81a0eb6?context=repo)
* [Quay land page for `cpppythondevelopment/base`](https://quay.io/repository/cpppythondevelopment/base)
* Distributions: `ubuntu1910`, `ubuntu1904`, `ubuntu1804`,
  `debian10`, `debian9`, `centos8`, `centos7`
* Badges: 
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cpppythondevelopment/base)](https://hub.docker.com/repository/docker/cpppythondevelopment/base/general)
[![Docker Repository on Quay](https://quay.io/repository/cpppythondevelopment/base/status "Docker Repository on Quay")](https://quay.io/repository/cpppythondevelopment/base)

### Python Machine Learning (ML)
* [GitHub repsitory - Docker for Python (Jupyter, Pandas)](https://github.com/machine-learning-helpers/docker-python-jupyter)
* [Docker land page for `artificialintelligence/python-jupyter`](https://hub.docker.com/repository/docker/artificialintelligence/python-jupyter)
  + [Docker image page for `artificialintelligence/python-jupyter:ubuntu1804`](https://hub.docker.com/layers/artificialintelligence/python-jupyter/ubuntu1804/images/sha256-a1ca930d5c520dd66ab23e6b8122e761b7274044a8e5ac30b4adb2ad740e121b?context=repo)
* [Quay land page for `artificialintelligence/python-jupyter`](https://quay.io/repository/artificialintelligence/python-jupyter)
* Distributions: `ubuntu1810`, `ubuntu1804`,
  `debian9`, `centos7`
* Badges:
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/artificialintelligence/python-jupyter)](https://hub.docker.com/repository/docker/artificialintelligence/python-jupyter/general)
[![Docker Repository on Quay](https://quay.io/repository/artificialintelligence/python-jupyter/status "Docker Repository on Quay")](https://quay.io/repository/artificialintelligence/python-jupyter)

## Python bindiings for OpenTravelData (OPTD)
* [OpenTravelData (OPTD) Data Wrapper - Python Bindings](https://github.com/opentraveldata/python-opentraveldata)

## Python installation
* [How-to install Python virtual environment with `pyenv` and `pipenv`](https://github.com/machine-learning-helpers/induction-python/tree/master/installation/virtual-env)

# Procedures

## New Python stable version
* [Python releases](https://www.python.org/downloads/)

### Add the new Python version to the C++/Python Docker images
* Add the commands to install the new Python version in the Dockerfile files
  of all the distriibutions. For instance,
  [adding Python 3.8.2 to Ubuntu 18.04](https://github.com/cpp-projects-showcase/docker-images/blob/master/ubuntu1804/Dockerfile#L91)
```bash
$ cat ubuntu1804/Dockerfile
...
# Python 3.8.2
RUN pyenv install 3.8.2 && \
    pyenv global 3.8.2 && \
    pip install -U pip pipenv
RUN pyenv global system || echo "No default system version of Python. Sticking to 3.8.2"
...
```

* Keeping at least one of the older versions of Python (3.8.1 here)
  gives the downstream Docker images the time to catch up.

### Update the Python environment of the Python Jupyter Docker image
The ML Pythn Jupyter Docker images is built on top of the generic C++/Python
image, described in the section above. The Python version is therefore
controlled by that Docker image.

The Python virtual environment speccifications need however to be upgraded.
Files to update:
* [`.python-version`](https://github.com/machine-learning-helpers/docker-python-jupyter/blob/master/.python-version)
* [`Pipfile`](https://github.com/machine-learning-helpers/docker-python-jupyter/blob/master/Pipfile)
* [`Pipfile.lock`](https://github.com/machine-learning-helpers/docker-python-jupyter/blob/master/Pipfile.lock)

### Update the Python environment of the Python Alpine Docker image
The default Alpine vresion comes up with the latest Python stable version,
only a few days after that latter has been released. There is hence
no need to upgrade the Python version on the Alpine Doccker images.

The Python virtual environment speccifications need however to be upgraded.
Files to update:
* [`dash-starter/.python-version`](https://github.com/machine-learning-helpers/docker-python-alpine/blob/master/dash-starter/.python-version)
* [`Pipfile`](https://github.com/machine-learning-helpers/docker-python-alpine/blob/master/dash-starter/Pipfile)
* [`Pipfile.lock`](https://github.com/machine-learning-helpers/docker-python-alpine/blob/master/dash-starter/Pipfile.lock)

### Non Docker projects to update

#### Machine Learning (ML) induction

Reference:
[ML-related Python induction project](https://github.com/machine-learning-helpers/induction-python)

There are two folders in that project where the Python setup has to be updated:
* [Root folder](https://github.com/machine-learning-helpers/induction-python)
  + [`.python-version`](https://github.com/machine-learning-helpers/induction-python/blob/master/.python-version)
  + [`Pipfile`](https://github.com/machine-learning-helpers/induction-python/blob/master/Pipfile)
  + [`Pipfile.lock`](https://github.com/machine-learning-helpers/induction-python/blob/master/Pipfile.lock)
* [`ml_induction_python` folder](https://github.com/machine-learning-helpers/induction-python/tree/master/ml_induction_python)
  + [`.python-version`](https://github.com/machine-learning-helpers/induction-python/blob/master/ml_induction_python/.python-version)
  + [`Pipfile`](https://github.com/machine-learning-helpers/induction-python/blob/master/ml_induction_python/Pipfile)
  + [`Pipfile.lock`](https://github.com/machine-learning-helpers/induction-python/blob/master/ml_induction_python/Pipfile.lock)
  + [`requirements.txt`](https://github.com/machine-learning-helpers/induction-python/blob/master/ml_induction_python/requirements.txt)

#### Python bindings for OpenTravelData (OPTD)

References: 
* [Python OpenTravelData (OPTD) bindgs](https://github.com/opentraveldata/python-opentraveldata)
* [OpenTravelData on PyPi](https://pypi.org/project/opentraveldata/)

Files to update:
* [`.python-version`](https://github.com/opentraveldata/python-opentraveldata/blob/master/.python-version)
* [`Pipfile`](https://github.com/opentraveldata/python-opentraveldata/blob/master/Pipfile)
* [`Pipfile.lock`](https://github.com/opentraveldata/python-opentraveldata/blob/master/Pipfile.lock)
* (potentially) [`setup.py`](https://github.com/opentraveldata/python-opentraveldata/blob/master/setup.py)
* (potentially) [`pyproject.toml`](https://github.com/opentraveldata/python-opentraveldata/blob/master/pyproject.toml#L10)
* [`requirements.txt`](https://github.com/opentraveldata/python-opentraveldata/blob/master/requirements.txt)
* [`requirements-dev.txt`](https://github.com/opentraveldata/python-opentraveldata/blob/master/requirements-dev.txt)
* (potentially) [`.travis.yml`](https://github.com/opentraveldata/python-opentraveldata/blob/master/.travis.yml#L5)
* (potentially) [`tox.ini`](https://github.com/opentraveldata/python-opentraveldata/blob/master/tox.ini#L2)

Publish the component on PyPi:
```bash
user@laptop$ cd ~/dev/geo/python-opentraveldata
user@laptop$ rm -rf dist && mkdir dist
user@laptop$ pipenv run python setup.py sdist bdist_wheel
user@laptop$ PYPIURL="https://test.pypi.org"
user@laptop$ pipenv run twine upload -u __token__ --repository-url ${PYPIURL}/legacy/ dist/*
user@laptop$ PYPIURL="https://pypi.org"
user@laptop$ #pipenv run keyring set ${PYPIURL}/ __token__
user@laptop$ pipenv run twine upload -u __token__ --non-interactive dist/*
```

#### Python bindings for OpenTREP

References:
* [(Python) OpenTREP Wrapper](https://github.com/trep/wrapper)
* [OpenTrepWrapper on PyPi](https://pypi.org/project/OpenTrepWrapper/)

Files to update:
* [`.python-version`](https://github.com/trep/wrapper/blob/master/.python-version)
* [`Pipfile`](https://github.com/trep/wrapper/blob/master/Pipfile)
* [`Pipfile.lock`](https://github.com/trep/wrapper/blob/master/Pipfile.lock)

Publish the component on PyPi:
```bash
user@laptop$ rm -rf dist && mkdir dist
user@laptop$ pipenv run python setup.py sdist bdist_wheel
user@laptop$ PYPIURL="https://test.pypi.org"
user@laptop$ pipenv run twine upload -u __token__ --repository-url ${PYPIURL}/legacy/ dist/*
user@laptop$ PYPIURL="https://pypi.org"
user@laptop$ #pipenv run keyring set ${PYPIURL}/ __token__
user@laptop$ pipenv run twine upload -u __token__ --non-interactive dist/*
```
