# MobiledgeX Docker NodeJS Hello World

If you are tired of struggling with installing compilers or are just starting out in the wonderful world of programming, this is the tutorial for you. We use the Docker software in an alternative way that helps you develop faster and more consistently. By using Docker in combination with your desired programming langague, you can create, manage and share your software much more easily. 

While Docker is a tool that is used to create standarized development and deployment containers for production software, it's uses go far beyond simply an enterprise deployment tool. Upon completion of this tutorial, you will have a working process where you can create, test and deploy code without having to install programming related software and struggle with compability and installation issues.

If you are new to docker, [this page](https://docs.docker.com/engine/examples/) is a handy reference glossary (https://docs.docker.com/glossary/) on the docker.com website. There you can find a comprehensive vocabulary list to help speed up the learning process.

## Prerequisites
For this tutorial, you will need:

*A computer running MacOS xx.xx.xx 
*[Chrome browser]() installed
*Know how to open a [terminal window](https://www.wikihow.com/Open-a-Terminal-Window-in-Mac)
*Know how to [navigate within a terminal window](https://www.youtube.com/watch?v=Vhcx4KJbtes)
*Have a basic understanding of programming

## Why Docker? ##
"Docker is an application delivery technology, not a virtualization technology..." This was the key statement in the [Docker blog](https://blog.docker.com/2016/03/containers-are-not-vms/) that helped me understand what Docker is and why it's important. In a nutshell, you can streamline development processes from ramp up to delivery and to support. 

Here are some additional links that can help you understand the benefits of Docker beyond simply being a requirement for the MobiledgeX platform:
*https://www.capside.com/labs/using-docker-for-development/ 
*https://codeburst.io/the-advantages-of-using-docker-for-web-development-23096c457fad

## Step 1 -- Install Docker ##

Install the Docker software on your system:  
    * [Install Docker Software on Mac](https://docs.docker.com/docker-for-mac/)
    * [Install Docker Software on Windows](https://docs.docker.com/docker-for-windows/)

[This tutorial](https://docs.docker.com/docker-hub/) will cover the basics for the following:
* Create your Docker account @ https://hub.docker.com/ 
* Create your first Docker “repo” on the Docker hosted [repository](https://docs.docker.com/glossary/?term=repository)
* Make sure to stop at Step 3. Do not complete Step 4 of the Docker Setup Tutorial as we will save that for later

Reference Documentation:
I found these additional youtube videos and blog guides helpful: 
*[Docker Tutorial - What is Docker & Docker Containers, Images, etc?](https://www.youtube.com/watch?v=pGYAg7TMmp0)

## Step 2 -- Create the Demo Files ##
There are amazingly few steps required to create a Docker image. You really only need a file called "dockerfile" to tell Docker how it needs to function and then your codebase. 
* Create a temporary folder
    * Create the following files within the temporary folder
        * “dockerfile” -- This file has no extension. This file lists Docker dependencies and tells Docker how to load your container
        * “package.json” -- This file lists NodeJS dependencies and any additional external libaries that you might want to include
        * "index.html" -- This file can be anything that you would like and only exists to visually show that y
* Optional -- download all files from the MobiledgeX Hello World github repository

## Step 3 -- Build the Demo ##
Open a terminal and navigate to the directory that contains the files you just created. Then, type the following command (everything that is highlighted in gray):  

` docker build . -t mobiledgex_hello_world:1 `

Format -- | docker build . -t <app name>:<version number> |

["docker build” command reference](https://docs.docker.com/engine/reference/commandline/build/)
    
    * “-t” -- Name the container “mobiledex_hello_world and tag the container with the tag of “latest”
    * Reference -- [tagging containers](https://stackoverflow.com/questions/41984399/denied-requested-access-to-the-resource-is-denied-docker) -- As a good practice, avoid using the word "latest" when tagging your container. Insteal, use numbers and letters so that you ensure Docker will pick up the file changes. 

## Step 4 -- Run the Demo! ##
This command is to run the container that you just built in the last step (everything that is highlighted in gray): 

` docker run -it -p 8000:8000 mobiledgex_hello_world:1 `

    * ["docker run" command reference](https://docs.docker.com/engine/reference/commandline/run/)
    * “-it” or “interactive” -- run the image interactively with a pseudo-tty
    * “-p” or “-publish” -- map the port 8000 in the container to port 8000 of your machine

Finally, open a browser window and go to localhost:8000 to verify that the Docker container did indeed load.