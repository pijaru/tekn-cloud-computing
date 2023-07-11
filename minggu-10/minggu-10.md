## Docker Networking Hands-on Lab
In this lab you will learn about key Docker Networking concepts. You will get your hands dirty by going through examples of a few basic networking concepts, learn about Bridge networking, and finally Overlay networking.

## Section #1 - Networking Basics

Step 1: The Docker Network Command
<img src="/images/10.1.png" alt="Getting started" />

Step 2: List networks
Run a docker network ls command to view existing container networks on the current Docker host.
<img src="/images/10.2.png" alt="Getting started" />

Step 3: Inspect a network
The docker network inspect command is used to view network configuration details. These details include; name, ID, driver, IPAM driver, subnet info, connected containers, and more.

Use docker network inspect <network> to view configuration details of the container networks on your Docker host. The command below shows the details of the network called bridge.
<img src="/images/10.3.png" alt="Getting started" />

Step 4: List network driver plugins
The docker info command shows a lot of interesting information about a Docker installation.

Run the docker info command and locate the list of network plugins.
<img src="/images/10.4.png" alt="Getting started" />

## Section #2 - Bridge Networking
Step 1: The Basics
Every clean installation of Docker comes with a pre-built network called bridge. Verify this with the docker network ls.
<img src="/images/10.5.png" alt="Getting started" />

Install the brctl command and use it to list the Linux bridges on your Docker host. You can do this by running sudo apt-get install bridge-utils.
<img src="/images/10.6.png" alt="Getting started" />
<img src="/images/10.7.png" alt="Getting started" />

Then, list the bridges on your Docker host, by running brctl show.
<img src="/images/10.8.png" alt="Getting started" />

The output above shows a single Linux bridge called docker0. This is the bridge that was automatically created for the bridge network. You can see that it has no interfaces currently connected to it.

You can also use the ip a command to view details of the docker0 bridge.
<img src="/images/10.9.png" alt="Getting started" />

## Step 2: Connect a container
The bridge network is the default network for new containers. This means that unless you specify a different network, all new containers will be connected to the bridge network.

Create a new container by running docker run -dt ubuntu sleep infinity.
<img src="/images/10.10.png" alt="Getting started" />

This command will create a new container based on the ubuntu:latest image and will run the sleep command to keep the container running in the background. You can verify our example container is up by running docker ps.
<img src="/images/10.11.png" alt="Getting started" />

You can inspect the bridge network again, by running docker network inspect bridge, to see the new container attached to it.
<img src="/images/10.12.png" alt="Getting started" />

## Step 3: Test network connectivity
Ping the IP address of the container from the shell prompt of your Docker host by running ping -c5 <IPv4 Address>. Remember to use the IP of the container in your environment.
<img src="/images/10.13.png" alt="Getting started" />

First, we need to get the ID of the container started in the previous step. You can run docker ps to get that.
<img src="/images/10.14.png" alt="Getting started" />

Next, lets run a shell inside that ubuntu container, by running docker exec -it <CONTAINER ID> /bin/bash.
<img src="/images/10.15.png" alt="Getting started" />

Next, we need to install the ping program. So, lets run apt-get update && apt-get install -y iputils-ping.
<img src="/images/10.16.png" alt="Getting started" />

Lets ping www.github.com by running ping -c5 www.github.com
<img src="/images/10.17.png" alt="Getting started" />
