# Using IBM J9 JVM Docker images in Travis.ci
This project is a very simple example showing how to use IBM Java docker images in travis.ci environment.  
Docker images containing the IBM JVM (J9) are available from: https://hub.docker.com/r/ibmcom/ibmjava/

This repository shows a "Hello World" class being compiled and run using the IBM J9 Java Docker images.  The `.travis.yml` 
pulls the '8-sdk' image, mounts the current directory as '/work', and then invokes the docker image to compile and run.

The three commands are:
- docker pull ibmcom/ibmjava:8-sdk
- docker run -v `pwd`:/work ibmcom/ibmjava:8-sdk /bin/sh -c "javac /work/Main.java"
- docker run -v `pwd`:/work ibmcom/ibmjava:8-sdk /bin/sh -c "java -cp work Main"
