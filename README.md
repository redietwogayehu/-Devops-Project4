[![CircleCI](https://dl.circleci.com/status-badge/img/gh/redietwogayehu/-Devops-Project4/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/redietwogayehu/-Devops-Project4/tree/main)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API.

You are given a pre-trained, sklearn model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on the data source site. This project tests your ability to operationalize a Python flask app—in a provided file, app.py—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

Project Tasks
Your project goal is to operationalize this working, machine learning microservice using kubernetes, which is an open-source system for automating the management of containerized applications. In this project you will:

Test your project code using linting
Complete a Dockerfile to containerize this application
Deploy your containerized application using Docker and make a prediction
Improve the log statements in the source code for this application
Configure Kubernetes and create a Kubernetes cluster
Deploy a container using Kubernetes and make a prediction
Upload a complete Github repo with CircleCI to indicate that your code has been tested
You can find a detailed project rubric, here.

The final implementation of the project will showcase your abilities to operationalize production microservices.

Setup the Environment
Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv.
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
Run make install to install the necessary dependencies
Running app.py
Standalone: python app.py
You will now access the app on localhost port 80. http://localhost:80

Run in Docker: bash run_docker.sh This script will:
Build an docker image
List images to verify that this app is dockerized
Run a container with this specified image and map port 8000 (host) to 80 (container)
You can now access the app on localhost port 8000. http://localhost:8000

Run in Kubernetes: bash run_kubernetes.sh The script will:
Start to run a container in Kubernetes cluster (make sure to have one ready the best option to locally is use minikube)
Wait for the pod to be running
List pod to verify your pod is up
Forward port 8000 (host) to 80 (container)
You can now access the app on localhost port 8000. http://localhost:8000

Files structure
.circleci/config.yml folder with the configuration to CircleCI
model_data folder with the trained model and data for prediction
output_txt_files folder with docker and kubernetes outputs files
app.py application script
Dockerfile use this file to deploy an image for the app to be runned on a container
make_prediction.sh script to test application
Makefile useful commands to make setup, install, test, lint, run_docker, run_kubernetes, upload_docker, all
requirements.txt dependencies of app
run_docker.sh script to build and start container
run_kubernetes.sh script to run on Kubernetes
upload_docker.sh script to upload to dockerhub container
Test the app
You can test this application by running the script bash make_prediction.sh,
