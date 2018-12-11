# Hands-on exercise

## Basic Shell (bash) concepts
 * Echo command: ```echo "Hello"```
 * Echo command w variable: ```echo "Hello $USER"```
 * Again: ```echo "${UID}"```

## Prepare the environment
 * Change to your home directory: ```cd ~```
 * Remove existing files from source: ```rm -rf ~/source/*```
 * Change into the source directory: ```cd ~/source```
 * Extract starter files: ```tar xzvf /opt/lab/docker.tar.gz ```

## Basic Docker Commands
 * Check the docker version: ```docker version```
 * Show the running docker containers: ```docker ps```
 * Show the docker images: ```docker image ls```

## Build Apache2 docker image
 * Change into the correct directory: ```cd ~/source/learning_lab```
 * Build a tagged image: 
 
 ```docker build -t ${USER}-apache2 webserver```
 
Remove the comments from the Docker file, repeat the above

## Run the Apache2 docker image with the specified TCP/IP port
In the following command, the TCP port on the host will equal 10000 + your UID 
 * Run the tagged image as a container: 
 ```
 docker run -dit --name ${USER}-running-app -p $(expr 10000 + ${UID}):80 ${USER}-apache2
 ```
 
 * Show the running containers: ```docker ps```
 * Stop the container: ```docker stop ${USER}-running-app```
 * Remove the container: ```docker rm ${USER}-running-app```

## Run the Apache2 docker image with the specified TCP/IP port
In the following command, the TCP port on the host will equal 10000 + your UID, content will come from the 'Kitty' directory. 
 * Run the tagged image as a container: 
 ```
 docker run -dit --name ${USER}-kitty-app \
 -v ${HOME}/source/learning_lab/Kitty:/usr/local/apache2/htdocs/ \
 -p $(expr 10000 + ${UID}):80 \
 ${USER}-apache2
 ```
 * Stop the container: ```docker stop ${USER}-kitty-app```
 * Remove the container: ```docker rm ${USER}-kitty-app```

