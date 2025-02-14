Accelergy-Timeloop Infrastructure
---------------------------------------------------

This docker aims to provide an experimental environment for easy plug-and-play of examples that run on the accelergy-timeloop DNN accelerator evaluation infrastructure. 
You can also use the src included in this docker to perform native installation of the tools. 

See instructions for both options below

This docker is modified based on: https://github.com/jsemer/timeloop-accelergy-tutorial

Native Install
-----------------

```
      % git clone --recurse-submodules https://github.com/Accelergy-Project/accelergy-timeloop-infrastructure.git
      % cd accelergy-timeloop-infrastructure
      % make pull
      % cd src/  # check all the sources here
      % to install all the tools: http://accelergy.mit.edu/infra_instructions.html
```

Start the container
-----------------

- Put the *docker-compose.yaml* file in an otherwise empty directory
- Cd to the directory containing the file
- Edit USER_UID and USER_GID in the file to the desired owner of your files (echo $UID, echo $GID)
- Run the following command:
```
      % docker-compose run infrastructure 
```
- Follow the instructions in the REAME directory to get public examples for this infrastructure


Refresh the container
----------------------

To update the Docker container run:

```
     % docker-compose pull
````



Build the image
---------------

```
      % git clone --recurse-submodules https://github.com/Accelergy-Project/accelergy-timeloop-infrastructure.git
      % cd accelergy-timeloop-infrastructure
      % export DOCKER_EXE=<name of docker program, e.g., docker>
      % make pull
      % make build [BUILD_FLAGS="<Docker build flags, e.g., --no-cache>"]
```

Push the image to docker hub
----------------------------

```
      % cd accelergy-timeloop-infrastructure
      % export DOCKER_NAME=<name of user with push privileges>
      % export DOCKER_PASS=<password of user with push privileges>
      % make push
```
