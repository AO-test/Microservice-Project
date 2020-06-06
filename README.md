[![CircleCI](https://circleci.com/gh/josh-iCode/Microservice-Project.svg?style=svg)](https://circleci.com/gh/josh-iCode/Microservice-Project)


## Project Overview

This project deployed a Machine Learning predictions model in to determince the price of houses in Boston, USA. 

A pre-trained, `sklearn` model has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.
This project was built using AWS Cloud9 environment which already has Docker and Virtual Box installed, thereby lifting off the stress of having to go through the installation and configuration off us. What you need install are [Hadolint](https://github.com/hadolint/hadolint) and [Kubernetes(Minikube)](https://kubernetes.io/docs/tasks/tools/install-minikube/). 

### Creating the Project

This project operationalized machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. The following steps were taken to actiualize this objective:
* Testing the project code using linting
* Creating a Dockerfile to containerize the application
* Deployment of the containerized application using Docker
* Creating a log statements in the source code for this application
* Configuration of Kubernetes and creation of a Kubernetes cluster
* Deployment of a container using Kubernetes and then make a prediction afterwards
* Uploading a complete Github repo with CircleCI to indicate that the code has been tested

---

## Setup the Environment

* Create a virtualenv and activate it by running the following commands one after the other:
  - python3 -m venv ~/.virtual-environment-name
  - source ~/.virtual-environment-name/bin/activate
* Create a requirements.txt file which would include the list of all the packages you'd like have to installed. 
* Run `make install` to install the necessary dependencies
* Run `make lint` to ensure that hadolint doesn't catch any errors in your Dockerfile and your code is rated 10/10

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`
4. To upload the docker image to your Docker hub by running the script `upload_docker.sh`
5. Create a directory `.circleci` and create a configuration file `config.yml` inside of it to integrate CircleCI

### Making prediction
* Run Docker shell script on another terminal: `make_predictions.sh` To make house price predictions (example of expected output can be found in the `docker_out.txt` file)
* Run Kubernetes shell script on another terminal: `make_predictions.sh` To make house price predictions (Example of expected output can be found in the`kubernetes_out.txt` file)
 


### Steps to run app in a local kubernetes cluster
* Setup and Configure [Docker](https://docs.docker.com/get-docker/) locally (You need to have a docker account)
* Setup and Configure [Kubernetes(Minikube)](https://kubernetes.io/docs/tasks/tools/install-minikube/)
* Create Flask app in Container
* Run via kubectl

