[![CircleCI](https://circleci.com/gh/thiruvarasamoorthy-viswanathan/project-ml-microservice-kubernetes/tree/main.svg?style=svg)](https://circleci.com/gh/thiruvarasamoorthy-viswanathan/project-ml-microservice-kubernetes/tree/main)

Docker Link: https://hub.docker.com/r/vtm1983/udacity-devops-project4/tags

## Project Summary

In this project, applied the skills I have acquired in this course to operationalize a Machine Learning Microservice API. 

Given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. 
we need read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests the ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. 

In this project, created the environemnt and Docker Image was created and deployed using Kubernetes. CircleCI was used to automation

### Project Tasks Carried out

Project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project:
* Test project code using linting
* Completed a Dockerfile to containerize this application
* Deployed containerized application using Docker and make a prediction
* Improved the log statements in the source code for this application
* Configured Kubernetes and create a Kubernetes cluster
* Deployed a container using Kubernetes and make a prediction
* Uploaded a complete Github repo with CircleCI to indicate that code has been tested


## Setup the Environment
Listed out all the commands used

* Created a virtualenv with Python 3.7 and activated it. 
```bash
git clone https://github.com/udacity/DevOps_Microservices.git
cd DevOps_Microservices/project-ml-microservice-kubernetes
python3 -m venv ~/.devops
source ~/.devops/bin/activate
make install
docker --version
wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3/hadolint-Linux-x86_64
sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3/hadolint-Linux-x86_64
sudo chmod +x /bin/hadolint
make lint
kubectl version
brew install minikube
 curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
 chmod +x ./kubectl
 sudo mv ./kubectl /usr/local/bin/kubectl
 kubectl version --client
 ```
* Run `make install` to install the necessary dependencies

### Running `app.py`
```bash
make lint
./run_docker.sh
docker image ls
docker run -p 8000:80 udacity-devops-project4
 ```

Run in Docker:
run_docker.sh contains the script to run the app in the docker.

./run_docker.sh

Run in Kubernetes:
run_kubernetes.sh contains the script to run app in the Kubernetes.
./make_prediction.sh

Upload to Docker Hub upload_docker.sh contains the script to upload the docker image to the Docker Hub.

./upload_docker.sh

### File Structure

1. sh files - run_docker, run_kubernetes, upload_docker updated with required scripts
2. Docker file - Updated the required statements
3. appy.py - Log statement included
4. docker_out.txt - placed inside output_txt_files folder which has the logs of the docker output
5. kubernetes_out - placed inside output_txt_files folder which has the logs of the Kubernetes output
6. Circleci/Config.yml - created a folder cirecleci and created the config.yml file

All the files/folders are in git root folder
