[![CircleCI](https://circleci.com/gh/markanr/udacity-project-5.svg?style=svg)](https://circleci.com/gh/markanr/udacity-project-5)

## Project Overview

This project was part of the AWS Cloud DevOps course, the goal was to set up a given flask app with a pre-trained 'sklearn' model that has been trained to predict housing prices in Boston according to several features. The flask application was containerized using docker, deployed locally for testing and debbuging purposes using kubernetes, linted using hadolint and pylint and builded via circleci.

## Project files

* ``` .circleci/config.yml ``` contains instructions for circleci on how to deploy the app
* ``` model_data ``` folder containing the pre-trained model for predictioning
* ``` output_txt_files ``` folder that contains output log files of docker and kubernetes runs
* ``` app.py ``` flask app for predicting housing prices
* ``` Dockerfile ``` which creates a docker container, creating a work directory, copying the flask app and installing dependencies defined in requirements.txt
* ``` make_predictions.sh ``` script for sending requests to the API
* ``` Makefile ``` file which sets up a virtual environment, installs dependencies and executes lint checks for Dockerfile and app.py
* ``` requirements.txt ``` containing needed dependencies
* ``` run_docker.sh ``` for building and running docker images
* ``` run_kubernetes.sh ``` for deploying the app using kubernetes
* ``` upload_docker.sh ``` for uploading the created image to dockerhub

## Guide

This part of the readme describes how to run the application, run the following commands to make the app work

1. ``` ./run_docker.sh  ```
    This builds the docker image and runs the same image in a container
2. ``` ./make_predictions.sh ```
    This sends a request to the container, useful for testing purposes
3. ``` ./upload_docker.sh ```
    If a payload is successfully sent in step 2, run the upload_docker.sh script to upload the image to dockerhub
4. ``` ./run_kubernetes.sh ```
    This script deploys the aplication using kubectl


### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
