[![CircleCI](https://circleci.com/gh/willyngeno/project-ml-microservice-kubernetes.svg?style=svg)](https://circleci.com/gh/willyngeno/project-ml-microservice-kubernetes)
With the help of kubernetes, an open-source solution for automating the maintenance of containerized applications, this project operationalizes a machine learning microservice. a pre-trained sklearn model that has been taught to forecast housing costs in Boston based on a variety of characteristics, including the average number of rooms in a home and information on highway accessibility, teacher-to-student ratios, and other factors. On the website for the data source, you can learn more about the data, which was originally acquired from Kaggle. In a given file called app.py, this project operationalizes a Python flask application that uses API calls to deliver predictions (inference) about housing prices. Any pre-trained machine learning model, such as those for image recognition and data labeling, could be included in this project.
## :page_with_curl:  _Instructions_

**1)** Fire up your favourite console & clone this repo somewhere:
git clone https://github.com/willyngeno/project-ml-microservice-kubernetes.git

**2)** Enter this directory:

__`❍ cd project-ml-microservice-kubernetes`__

**3)** Install [python](https://www.python.org/) if not already installed and run this command to create a virtual environment and activate it:

__`❍ make setup`__

**4)** Run this command to install the project dependencies:

__`❍ make install`__

**5)** Run this command to lint the project files:

__`❍ make lint`__

**6)** Run this script to build a docker image for the app and start the app in a docker container:

__`❍ ./run_docker.sh `__

**7)** Run this script to get a prediction from the app running in the Docker container:

__`❍ ./make_prediction.sh `__

**8)** Run this script to upload the docker image to your Docker hub account. Note you'll have to edit the script and change the Docker ID to yours:

__`❍ ./upload_docker.sh `__

**9)** Run this script to run the service in a kubernetes cluster. You'll be making use of my image repo. You can edit the script and change to your image repo on Docker hub if you've built and pushed your image. This script will be run twice to activate the port forwarding. Give some minutes after first run so that the pod can be up and running before attempting port forwarding:

__`❍ ./run_kubernetes.sh `__

**10)** Run this script to get a prediction from the app running in the Kubernetes Cluster after port forwarding is successful:

__`❍ ./make_prediction.sh `__

&nbsp;

## :information_source: Files:

* app.py: This is the flask app that runs the service
* Makefile: This file has make commands that allows for easy setup of a project
* Dockerfile: This file has the setup for creating a Docker image for the microservice
* run_docker.sh: This script creates a docker image from the Dockerfile, list the images and starts a container
* make_prediction.sh: This script sends data for prediction using curl and prints the predicted value on the command line
* upload_docker.sh: This script uploads a docker image to docker hub
* run_kubernetes.sh: This script runs the docker image in a kubernetes cluster

&nbsp;

__*Happy developing!*__
