Management of Python-related Docker images
==========================================

Python wrapper around OpenTravelData (OPTD) data sets, for instance
to be used by Python software needing to access OPTD data.

# References
* [This GitHub repository - Docker Image Management](https://github.com/python-helpers/docker-image-management)

## Projects this repository helps to manage

### Docker light (Alpine) images to support Machine Learning (ML) in Python
* [ML Helpers GitHub repository](https://github.com/machine-learning-helpers/docker-python-alpine)
* [Docker land page for `artificialintelligence/python-alpine`](https://hub.docker.com/repository/docker/artificialintelligence/python-alpine)
  + [Docker image page for `artificialintelligence/python-alpine:alp311`](https://hub.docker.com/layers/artificialintelligence/python-alpine/alp311/images/sha256-ad89caf67586d26c9ee1f187bb781a63856c3c8ea8b20a7b0785d71170359091?context=repo)
* [Quay land page for `artificialintelligence/python-alpine`](https://quay.io/repository/artificialintelligence/python-alpine)
* Distributions: `alpine-3.11`, `py37-alp311`
* Badges:
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/artificialintelligence/python-alpine)](https://hub.docker.com/repository/docker/artificialintelligence/python-alpine/general)
[![Docker Repository on Quay](https://quay.io/repository/artificialintelligence/python-alpine/status "Docker Repository on Quay")](https://quay.io/repository/artificialintelligence/python-alpine)

### Docker images to support development on C++ and Python stacks

#### General C++/Python development
* [GitHub repsitory - Docker for C++ development](https://github.com/cpp-projects-showcase/docker-images)
* [Docker land page for `cpppythondevelopment/base`](https://hub.docker.com/repository/docker/cpppythondevelopment/base)
  + [Docker image page for `cpppythondevelopment/base:ubuntu1804`](https://hub.docker.com/layers/cpppythondevelopment/base/ubuntu1804/images/sha256-d79bb20ef0ed2eb2e474ea06806b69ac95d36de6056ce9185eb9a904e81a0eb6?context=repo)
* [Quay land page for `cpppythondevelopment/base`](https://quay.io/repository/cpppythondevelopment/base)
* Distributions: `ubuntu1910`, `ubuntu1904`, `ubuntu1804`,
  `debian10`, `debian9`, `centos8`, `centos7`
* Badges: 
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cpppythondevelopment/base)](https://hub.docker.com/repository/docker/cpppythondevelopment/base/general)
[![Docker Repository on Quay](https://quay.io/repository/cpppythondevelopment/base/status "Docker Repository on Quay")](https://quay.io/repository/cpppythondevelopment/base)

#### Python Machine Learning (ML)
* [GitHub repsitory - Docker for Python (Jupyter, Pandas)](https://github.com/machine-learning-helpers/docker-python-jupyter)
* [Docker land page for `artificialintelligence/python-jupyter`](https://hub.docker.com/repository/docker/artificialintelligence/python-jupyter)
  + [Docker image page for `artificialintelligence/python-jupyter:ubuntu1804`](https://hub.docker.com/layers/artificialintelligence/python-jupyter/ubuntu1804/images/sha256-a1ca930d5c520dd66ab23e6b8122e761b7274044a8e5ac30b4adb2ad740e121b?context=repo)
* [Quay land page for `artificialintelligence/python-jupyter`](https://quay.io/repository/artificialintelligence/python-jupyter)
* Distributions: `ubuntu1810`, `ubuntu1804`,
  `debian9`, `centos7`
* Badges:
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/artificialintelligence/python-jupyter)](https://hub.docker.com/repository/docker/artificialintelligence/python-jupyter/general)
[![Docker Repository on Quay](https://quay.io/repository/artificialintelligence/python-jupyter/status "Docker Repository on Quay")](https://quay.io/repository/artificialintelligence/python-jupyter)

### Python bindiings for OpenTravelData (OPTD)
* [OpenTravelData (OPTD) Data Wrapper - Python Bindings](https://github.com/opentraveldata/python-opentraveldata)

### Python installation
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

### Update the Python environment of  the Python Alpine Docker image
The default Alpine vresion comes up with the latest Python stable version,
only a few days after that latter has been released. There is hence
no need to upgrade the Python version on the Alpine Doccker images.

The Python virtual environment speccifications need however to be upgraded.
Files to update:
* [`dash-starter/.python-version`](https://github.com/machine-learning-helpers/docker-python-alpine/blob/master/dash-starter/.python-version)
* [`Pipfile`](https://github.com/machine-learning-helpers/docker-python-alpine/blob/master/dash-starter/Pipfile)
* [`Pipfile.lock`](https://github.com/machine-learning-helpers/docker-python-alpine/blob/master/dash-starter/Pipfile.lock)


