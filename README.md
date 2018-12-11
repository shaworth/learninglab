# Hands-on exercise

## Basic Shell (bash) concepts
 * Echo command: ```echo "Hello"```
 * Echo command with variable: ```echo "Hello $USER"```

## Prepare the environment
 * Remove existing files from source: ```rm -rf ~/source/*```
 * Change into the source directory: ```cd ~/source```
 * Extract starter files: ```tar xzvf /opt/lab/docker.tar.gz ~/source/```

## Basic Docker Commands
 * Check the docker version: ```docker version```
 * Show the running docker containers: ```docker ps```
 * Show the docker images: ```docker image ls```

## Build Apache2 docker image
 * Change into the correct directory: ```cd ~/source/learning_lab```
 * Build a tagged image: ```docker build -t ${USER}-apache2 webserver```

## Run the Apache2 docker image
 * Run the tagged image: ```docker run -dit --name ${USER}-running-app -p 8080:80 ${USER}-apache2
 
