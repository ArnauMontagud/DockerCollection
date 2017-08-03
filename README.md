Description
===========

Collection of Docker images:
`logical_pipeline` is a Docker image containing all scripts and tools from our [logical modelling pipeline](https://github.com/sysbio-curie/Logical_modelling_pipeline) as well as all the packages that allow them to run. This image's Dockerfile has code from [buildpack-deps/stretch/curl](https://github.com/docker-library/buildpack-deps/blob/9f60e19008458220114f1a0b6cd3710f1015d402/stretch/curl/Dockerfile), [openjdk/8-jre](https://github.com/docker-library/openjdk/blob/b4f29ba829765552239bd18f272fcdaf09eca259/8-jre/Dockerfile), [rocker-org/rocker-versioned/r-ver/3.4.1](https://github.com/rocker-org/rocker-versioned/blob/master/r-ver/3.4.1/Dockerfile) and [rocker-org/rocker-versioned/rstudio/3.4.1](https://github.com/rocker-org/rocker-versioned/blob/master/rstudio/3.4.1/Dockerfile)

Usage
=====

To use the `logical_pipeline` docker image, it is necessary, after installing [Docker](https://www.docker.com), to run the following type:

    docker pull arnaumontagud/logical_modelling_pipeline

Before doing anything please else, please take note of your local Docker machine's IP using:
 
    docker-machine ip default

We recommend that you copy or clone the contents of the [logical modelling pipeline GitHub repository](https://github.com/sysbio-curie/Logical_modelling_pipeline) and mount that folder on the Docker container using the `-v` flag when running it with the command

    docker run --rm -ti -p 8787:8787 -v "/{local_tutorial_folder}":/home/rstudio/data arnaumontagud/logical_modelling_pipeline

If you do not want to mount the local folder, the image can be started with the command:

    docker run --rm -ti -p 8787:8787 arnaumontagud/logical_modelling_pipeline

At this point, you will be able to use the terminal to run all the tutorial. In the parts in which you need to run R, run command

    /init
    
This will bring an RStudio web interface containing all the necessary packages. This web interface will be availabe, in Unix-like systems, at the address <http://localhost:8787> and in Windows systems at <http://your-local-Docker-machine's-IP:8787>. It is then possible to access the interface by using "rstudio" as the username and password.

If any problem is encountered using this RStudio image see the instructions [here](https://github.com/rocker-org/rocker/wiki/Using-the-RStudio-image).

After starting the interface, it is possible to write r code as in the desktop version of RStudio.
