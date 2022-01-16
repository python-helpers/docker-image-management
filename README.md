Management of Python-related tools and container images
=======================================================

# Table of Content (ToC)
- [Management of Python-related tools and container images](#management-of-python-related-tools-and-container-images)
- [Table of Content (ToC)](#table-of-content-toc)
- [Overview](#overview)
  * [References](#references)
- [Projects this repository helps to manage](#projects-this-repository-helps-to-manage)
  * [Light images to support Machine Learning (ML) in Python](#light-images-to-support-machine-learning-ml-in-python)
  * [Docker images to support development on C++ and Python stacks](#docker-images-to-support-development-on-c-and-python-stacks)
    + [General C++/Python development](#general-c-python-development)
    + [Python Machine Learning (ML)](#python-machine-learning-ml)
    + [Python cloud images](#python-cloud-images)
  * [Python tools for OpenTravelData (OPTD)](#python-tools-for-opentraveldata-optd)
  * [Quality Assurance (QA) for OpenTravelData (OPTD)](#quality-assurance-qa-for-opentraveldata-optd)
  * [Python bindings for OpenTravelData (OPTD)](#python-bindings-for-opentraveldata-optd)
  * [Python bindings for OpenTREP](#python-bindings-for-opentrep)
  * [Python installation](#python-installation)
- [Procedures](#procedures)
  * [New Python stable version](#new-python-stable-version)
    + [Add the new Python version to the C++/Python Docker images](#add-the-new-python-version-to-the-c-python-docker-images)
    + [Update the Python environment of the Python Jupyter Docker image](#update-the-python-environment-of-the-python-jupyter-docker-image)
    + [Update the Python environment of the Python light Docker image](#update-the-python-environment-of-the-python-light-docker-image)
    + [Non Docker projects to update](#non-docker-projects-to-update)
      - [Machine Learning (ML) induction](#machine-learning-ml-induction)
      - [Python tools for OpenTravelData (OPTD)](#python-tools-for-opentraveldata-optd-1)
      - [Quality Assurance (QA) for OpenTravelData (OPTD)](#quality-assurance-qa-for-opentraveldata-optd-1)
      - [Python bindings for OpenTravelData (OPTD)](#python-bindings-for-opentraveldata-optd)
      - [Python bindings for OpenTREP](#python-bindings-for-opentrep-1)
  * [Installation or update of a Python virtual environment](#installation-or-update-of-a-python-virtual-environment)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

# Overview

## References
* [This GitHub repository - Docker Image Management](https://github.com/python-helpers/docker-image-management)

# Projects this repository helps to manage

## Light images to support Machine Learning (ML) in Python
* [ML Helpers GitHub repository](https://github.com/machine-learning-helpers/docker-python-light)
* [Docker land page for `infrahelpers/python-light`](https://hub.docker.com/repository/docker/infrahelpers/python-light)
  + [Docker image page for `infrahelpers/python-light:py39-bullseye`](https://hub.docker.com/layers/173696157/infrahelpers/python-light/py39-bullseye/images/sha256-7b68b943693e3fd5528e5356e2e0eda97c002299d80b862caa15216843d8b8a7?context=repo)
* [Quay land page for `artificialintelligence/python-light`](https://quay.io/repository/artificialintelligence/python-light)
* Distributions:
  + [`py310-bullseye`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.10-bullseye/)
  + [`py310-buster`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.10-buster/)
  + [`py39-bullseye`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.9-bullseye/)
  + [`py39-buster`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.9-buster/)
  + [`py39-alp314`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.9-alpine-3.14)
  + [`py38-bullseye`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.8-bullseye/)
  + [`py38-buster`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.8-buster/)
  + [`py38-alp314`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/python-3.8-alpine-3.14)
  + [`alp314-py395`](https://github.com/machine-learning-helpers/docker-python-light/tree/master/docker/alpine-3.14/)
* Badges:
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/infrahelpers/python-light)](https://hub.docker.com/repository/docker/infrahelpers/python-light/general)
[![Docker Repository on Quay](https://quay.io/repository/artificialintelligence/python-light/status)](https://quay.io/repository/artificialintelligence/python-light)

## Docker images to support development on C++ and Python stacks

### General C++/Python development
* [GitHub repsitory - Docker for C++ development](https://github.com/cpp-projects-showcase/docker-images)
* [Docker land page for `infrahelpers/cpppython`](https://hub.docker.com/repository/docker/infrahelpers/cpppython)
  + [Docker image page for `infrahelpers/cpppython:ubuntu2004`](https://hub.docker.com/layers/infrahelpers/cpppython/ubuntu2004/images/sha256-94e8546efa4bf2266876696d9faaebeb013e527490c177c019b3d2c17154524b?context=repo)
* [Quay land page for `cpppythondevelopment/base`](https://quay.io/repository/cpppythondevelopment/base)
* Distributions: `ubuntu2004`, `ubuntu1804`, `ubuntu1604`,
  `debian11`, `debian10`, `centos8`, `centos7`, `fedora35`, `fedora34`
* Badges: 
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/infrahelpers/cpppython)](https://hub.docker.com/repository/docker/infrahelpers/cpppython/general)
[![Docker Repository on Quay](https://quay.io/repository/cpppythondevelopment/base/status "Docker Repository on Quay")](https://quay.io/repository/cpppythondevelopment/base)

### Python Machine Learning (ML)
* [GitHub repsitory - Docker for Python (Jupyter, Pandas)](https://github.com/machine-learning-helpers/docker-python-jupyter)
* [Docker land page for `infrahelpers/python-jupyter`](https://hub.docker.com/repository/docker/infrahelpers/python-jupyter)
  + [Docker image page for `infrahelpers/python-jupyter:ubuntu2004`](https://hub.docker.com/layers/173699360/infrahelpers/python-jupyter/ubuntu2004/images/sha256-cb46eb37d40f9fa20457fada31e8255d31d23846fa54e8d2db6178c6be437848?context=repo)
* [Quay land page for `artificialintelligence/python-jupyter`](https://quay.io/repository/artificialintelligence/python-jupyter)
* Distributions: `ubuntu2004`, `ubuntu1804`, `ubuntu1604`,
  `debian11`, `debian10`, `centos8`, `centos7`
* Badges:
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/infrahelpers/python-jupyter)](https://hub.docker.com/repository/docker/infrahelpers/python-jupyter/general)
[![Docker Repository on Quay](https://quay.io/repository/artificialintelligence/python-jupyter/status "Docker Repository on Quay")](https://quay.io/repository/artificialintelligence/python-jupyter)

### Python cloud images
* [GitHub repsitory - Python cloud images](https://github.com/cloud-helpers/cloud-python-images)
* [Docker land page for `infrahelpers/cloud-python`](https://hub.docker.com/repository/docker/infrahelpers/cloud-python)
  + [Docker image page for `infrahelpers/cloud-python:py39-buster`](https://hub.docker.com/layers/161395146/infrahelpers/cloud-python/py39-buster/images/sha256-fe7b350505965cacfcda41d9ad7e9492d56222a9822b9b5435b689093487d25f?context=repo)
* Distributions: `py310-bullseye`, `py310-buster`,
  `py39-bullseye`, `py39-buster`, `py38-bullseye`, `py38-buster`
* Badges:
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/infrahelpers/cloud-python)](https://hub.docker.com/repository/docker/infrahelpers/cloud-python/general)

## Python tools for OpenTravelData (OPTD)
* [OpenTravelData (OPTD) tools](https://github.com/opentraveldata/opentraveldata/blob/master/tools/)

## Quality Assurance (QA) for OpenTravelData (OPTD)
* [OpenTravelData (OPTD) - Quality Assurance (QA)](https://github.com/opentraveldata/quality-assurance/)

## Python bindings for OpenTravelData (OPTD)
* [OpenTravelData (OPTD) Data Wrapper - Python Bindings](https://github.com/opentraveldata/python-opentraveldata)
* [OpenTravelData (OPTD) on PyPi](https://pypi.org/project/opentraveldata/)

## Python bindings for OpenTREP
* [OpenTREP - Python wrapper](https://github.com/trep/wrapper)
* [OpenTrepWrapper on PyPi](https://pypi.org/project/OpenTrepWrapper/)

## Python installation
* [How-to install Python virtual environment with `pyenv` and `pipenv`](https://github.com/machine-learning-helpers/induction-python/tree/master/installation/virtual-env)

# Procedures

## New Python stable version
* [Python releases](https://www.python.org/downloads/)

### Add the new Python version to the C++/Python Docker images
* Git repository: https://github.com/cpp-projects-showcase/docker-images

* Add the commands to install the new Python version in the Dockerfile files
  of all the distriibutions. For instance,
  [adding Python 3.9.10 to Ubuntu 20.04](https://github.com/cpp-projects-showcase/docker-images/blob/master/ubuntu2004/Dockerfile#L127)
```bash
$ cat ubuntu2004/Dockerfile
...
# Python 3.9.10
RUN pyenv install 3.9.10 && \
    pyenv global 3.9.10 && \
    python -mpip install -U pip pipenv
RUN pyenv global system || echo "No default system version of Python. Sticking to 3.9.10"
...
```

* Keeping at least one of the older versions of Python (3.8.12 and 3.9.9 here)
  gives the teams managing downstream Docker images the time to catch up.

### Update the Python environment of the Python Jupyter Docker image
* Git repository:
  https://github.com/machine-learning-helpers/docker-python-jupyter

The ML Python Jupyter Docker images are built on top of the generic C++/Python
images, described in the section above. The Python versions are therefore
controlled by those Docker images.

The Python virtual environment specifications need however to be upgraded.
Files to update:
* [`.python-version`](https://github.com/machine-learning-helpers/docker-python-jupyter/blob/master/.python-version)
* [`Pipfile`](https://github.com/machine-learning-helpers/docker-python-jupyter/blob/master/Pipfile)
* [`Pipfile.lock`](https://github.com/machine-learning-helpers/docker-python-jupyter/blob/master/Pipfile.lock)

### Update the Python environment of the Python light Docker image
* Git repository:
  https://github.com/machine-learning-helpers/docker-python-light

The default Python versions for light images (_e.g._, Alpine, Debian and
Debian Slim), as maintained by Docker itself
([on GitHub](https://github.com/docker-library/python) and
[on Docker Hub](https://hub.docker.com/_/python)), are usually
the latest Python stable versions, only a few days after they have been
released. There is hence no need to upgrade the Python version on the
light Doccker images.

### Non Docker projects to update

#### Machine Learning (ML) induction

Reference:
[ML-related Python induction project](https://github.com/machine-learning-helpers/induction-python)

Note that this Git repository is also a sub-module of the
[Python Jupyter Docker image project](#update-the-python-environment-of-the-python-jupyter-docker-image)

There are two folders in that project where the Python setup has to be updated:
* [Root folder](https://github.com/machine-learning-helpers/induction-python)
  + [`.python-version`](https://github.com/machine-learning-helpers/induction-python/blob/master/.python-version)
  + [`Pipfile`](https://github.com/machine-learning-helpers/induction-python/blob/master/Pipfile)
  + [`Pipfile.lock`](https://github.com/machine-learning-helpers/induction-python/blob/master/Pipfile.lock)
* [`ml_induction_python` folder](https://github.com/machine-learning-helpers/induction-python/tree/master/ml_induction_python)
  + [`Pipfile`](https://github.com/machine-learning-helpers/induction-python/blob/master/ml_induction_python/Pipfile)
  + [`Pipfile.lock`](https://github.com/machine-learning-helpers/induction-python/blob/master/ml_induction_python/Pipfile.lock)
  + [`requirements.txt`](https://github.com/machine-learning-helpers/induction-python/blob/master/ml_induction_python/requirements.txt)

Then, the ML Docker project (see above) should be updated to point to
the new Python ML induction head.
* Clone the ML Docker project and initialize sub-modules (if needed):
```bash
$ mkdir -p ~/dev/ml && git clone https://github.com/machine-learning-helpers/docker-python-jupyter ~/dev/ml/docker-python-jupyter
$ cd ~/dev/ml/docker-python-jupyter
$ git submodule init
$ git submodule update --recursive --force
```

* Pull (with Git) the head of the `master` branch on the ML induction module:
```bash
$ cd ~/dev/ml/docker-python-jupyter/notebook/induction
$ git checkout master
$ git pull
```

* Add, commit and push (with Git) the newly updated module:
```bash
$ cd ~/dev/ml/docker-python-jupyter
$ git add notebook/induction
$ git commit -m "[Modules] Updated the Python ML induction module"
$ git push
```

#### Python tools for OpenTravelData (OPTD)

References:
* [OpenTravelData (OPTD) tools](https://github.com/opentraveldata/opentraveldata/blob/master/tools/)

Files to update:
* [`Pipfile`](https://github.com/opentraveldata/opentraveldata/blob/master/tools/Pipfile)
* [`Pipfile.lock`](https://github.com/opentraveldata/opentraveldata/blob/master/tools/Pipfile.lock)

#### Quality Assurance (QA) for OpenTravelData (OPTD)

References:
* [OpenTravelData (OPTD) - Quality Assurance (QA)](https://github.com/opentraveldata/quality-assurance/)

Files to update:
* [`Pipfile`](https://github.com/opentraveldata/quality-assurance/blob/master/Pipfile)
* [`Pipfile.lock`](https://github.com/opentraveldata/quality-assurance/blob/master/Pipfile.lock)
* [`requirements.txt`](https://github.com/opentraveldata/quality-assurance/blob/master/requirements.txt)
  + Copy that `requirements.txt` file as
    [`ci-scripts/requirements.txt` in OpenTravelData (OPTD)](https://github.com/opentraveldata/opentraveldata/blob/master/ci-scripts/requirements.txt)

#### Python bindings for OpenTravelData (OPTD)

References: 
* [Python OpenTravelData (OPTD) bindings](https://github.com/opentraveldata/python-opentraveldata)
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
* [`requirements-dev.txt `](https://github.com/trep/wrapper/blob/master/requirements-dev.txt)

Publish the component on PyPi:
```bash
user@laptop$ rm -rf dist && mkdir dist
user@laptop$ pipenv run python setup.py sdist bdist_wheel
user@laptop$ PYPIURL="https://test.pypi.org"
user@laptop$ pipenv run twine upload -u __token__ --repository-url ${PYPIURL}/legacy/ dist/*
user@laptop$ PYPIURL="https://pypi.org"
user@laptop$ #pipenv run keyring set ${PYPIURL}/ __token__
user@laptop$ pipenv run twine upload -u __token__ --non-interactive --repository-url ${PYPIURL}/legacy/ dist/*
```

Re-generate `requirements.txt` and `requirements-dev.txt`:
```bash
$ pipenv lock -r > requirements.txt
$ pipenv lock -r --dev > requirements-dev.txt
```

## Installation or update of a Python virtual environment
* In a folder governed by `Pipfile`:
  + To install the dedicated Python virtual environment:
```bash
$ pipenv install; pipenv install --dev
```
  + To update the dedicated Python virtual environment:
```bash
$ pipenv update
```

* On MacOS, with the `psycopg2` module, there may be some trouble
  at installation time related to an issue with SSL libraries. It can
  usually be solved with:
```bash
$ LDFLAGS="-I/usr/local/opt/openssl/include" CPPFLAGS="-L/usr/local/opt/openssl/lib" pipenv install psycopg2
Installing psycopg2
Adding psycopg2 to Pipfile's [packages]
✔ Installation Succeeded 
$ pipenv install; pipenv install --dev
```
