# Using docker-compose to run the protractor tests with selenium grid #

This is a basic setup to show how dockercan be used to run Protractor tests. We would setup a Selenium Grid and run the tests.

## Prerequisites ##

Docker needs to be installed on your machine, can be downloaded from: https://www.docker.com/

## Set up ##

Once docker is installed and running, download the docker images using the following commands in power shell

## Step 0: Download the docker images for Selenium Hub and Selenium Node ##

docker pull selenium/hub:latest
docker pull selenium/node-chrome:latest

## Step 1: Setting up Selenium Grid ##

docker run -d -p 4444:4444 --name selenium-hub selenium/hub:latest

## Step 2: Starting the Selenium Nodes ##

docker run -d --link selenium-hub:hub selenium/node-chrome:latest

## Step 3: Running the tests ##

C:/ node ./node_modules/.bin/protractor conf.js

# Using Docker Compose #

Docker compose can be used as one stop point for running all the images.

docker-compose up -d

References: 
To learn more, see the documentation for [Docker](https://docs.docker.com/) and [Protractor](http://www.protractortest.org/#/).
