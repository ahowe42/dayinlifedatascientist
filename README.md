# A Day in the Life of a Data Scientist
[This notebook](./notebooks/DayLifeDataScientist_overview.ipynb) summarizes the basic process and several of the stages of the data science process, essentially capturing a day in the life of a data scientist or statistical modeler.

Data prepration and exploration are demonstrated on a benchmark dataset, and machine learning modeling concepts are demonstrated using three models:
- Multiple Linear Regression
- Decision Tree Regression
- Simple Neural Network

# Python Environment
This repository includes the files needed to create a docker container which can run the code in this repository:
- Dockerfile_ubuntu: to build an ubuntu-based image with the requisite python installation and packages
- docker_compose.yaml: to build a docker app based on the above-mentioned dockerfile
- requirements.txt: list required python packages and versions
- supervisord.conf: supervisor configuration file

## Docker Build
From the repository folder, execute `docker compose up` to build the docker app. Then the jupyter notebook can be accessed on *localhost:9999*, and tensorboard (for the neural network) on *localhost:6006*. Otherwise, you can execute from the repository folder:
1. docker image build -t dayinlifedatascientist .
2. docker container run -d -p 9999:8888 -p 6006:6006 -v //path_to_folder/dayinlifedatascientist/notebooks:/usr/src/notebooks dayinlifedatascientist
