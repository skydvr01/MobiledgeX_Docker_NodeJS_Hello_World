# MobiledgeX Docker Hello World #

This tutorial walks through the process of creating a simple app that is "dockerized." You would want to dockerize your application because not only does it help with your application development process and pipeline, it is a requirement for deploying applications to the MobiledgeX platform.

(https://docs.docker.com/engine/examples/) A handy reference page for those of you new to Docker is the glossary page (https://docs.docker.com/glossary/) on the docker.com website. There you can find clear definitions of new vocabulary to help speed up the learning process.

## Tutorial Requirements ##

This tutorial assumes the following:
*You are using MacOS
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

Follow [this tutorial](https://docs.docker.com/docker-hub/) for the following:
    * Create your Docker account @ https://hub.docker.com/ 
    * Create your first Docker “repo”
    * Make sure to stop at Step 3. Do not complete Step 4 of the Docker Setup Tutorial as we will save that for later

Reference Documentation:
*[]()
    *[Docker Tutorial - What is Docker & Docker Containers, Images, etc?](https://www.youtube.com/watch?v=pGYAg7TMmp0)

## Step 2 -- Create the Demo Files ##
* Create a temporary folder
    * Create the following files within the temporary folder
        * “dockerfile” -- This file has no extension. This file lists Docker dependencies and tells Docker how to load your container
        * “package.json” -- This file lists NodeJS dependencies and any additional external libaries that you might want to include
        * "index.html" -- This file can be anything that you would like and only exists to visually show that y
* Optional -- download all files from the MobiledgeX Hello World github repository

## Step 3 -- Compile/Build Docker Commands ##
Open a terminal and navigate to the directory that contains the files you just created. Then, type the following command:  

` docker build . -t mobiledgex_hello_world:latest `

Format -- | docker build . -t <app name>:<version number> |

["docker build” command reference](https://docs.docker.com/engine/reference/commandline/build/)
    * “-t” -- Name the container “mobiledex_hello_world and tag the container with the tag of “latest”
    * Reference -- [tagging containers](https://stackoverflow.com/questions/41984399/denied-requested-access-to-the-resource-is-denied-docker) -- As a good practice, avoid using the word "latest" when tagging your container. Insteal, use numbers and letters so that you ensure Docker will pick up the file changes. 

## Step 4 -- Run Docker Image Locally ##
This command is to run the container that you just build locally to see if the container was built properly and/or that it runs. 

` docker run -it -p 8000:8000 mobiledgex_hello_world:latest `

"docker run" command reference

“-it” or “interactive” -- run the image interactively with a pseudo-tty

“-p” or “-publish” -- map the port 8000 in the container to port 8000 of your machine
