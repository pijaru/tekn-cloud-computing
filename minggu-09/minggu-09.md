## Docker for Beginners - Linux

### Clone the Lab’s GitHub Repo
Use the following command to clone the lab’s repo from GitHub (you can click the command or manually type it). This will make a copy of the lab’s repo in a new sub-directory called linux_tweet_app.
<img src="/images/9.1.png" alt="Getting started" />
<img src="/images/9.2.png" alt="Getting started" />

### Task 1: Run some simple Docker containers

#### Run the following command in your Linux console.
<img src="/images/9.3.png" alt="Getting started" />

#### List all containers.
<img src="/images/9.4.png" alt="Getting started" />

###  Run an interactive Ubuntu container
1. Run a Docker container and access its shell.
<img src="/images/9.5.png" alt="Getting started" />

2. Run the following commands in the container.
- ls /
<img src="/images/9.6.png" alt="Getting started" />

- ps aux
<img src="/images/9.7.png" alt="Getting started" />

- cat /etc/issue
<img src="/images/9.8.png" alt="Getting started" />

3. Type exit to leave the shell session. This will terminate the bash process, causing the container to exit.
<img src="/images/9.9.png" alt="Getting started" />

4. For fun, let’s check the version of our host VM.
<img src="/images/9.10.png" alt="Getting started" />

### Run a background MySQL container
1. Run a new MySQL container with the following command.
<img src="/images/9.11.png" alt="Getting started" />

2. List the running containers.
<img src="/images/9.12.png" alt="Getting started" />

3. You can check what’s happening in your containers by using a couple of built-in Docker commands: docker container logs and docker container top.
<img src="/images/9.13.png" alt="Getting started" />

Let’s look at the processes running inside the container.
<img src="/images/9.14.png" alt="Getting started" />

4. List the MySQL version using docker container exec.
<img src="/images/9.15.png" alt="Getting started" />

5. You can also use docker container exec to connect to a new shell process inside an already-running container. Executing the command below will give you an interactive shell (sh) inside your MySQL container.
<img src="/images/9.16.png" alt="Getting started" />

6. Let’s check the version number by running the same command again, only this time from within the new shell session in the container.
<img src="/images/9.17.png" alt="Getting started" />

### Task 2: Package and run a custom app using Docker
1. Make sure you’re in the linux_tweet_app directory.
<img src="/images/9.18.png" alt="Getting started" />

2. Display the contents of the Dockerfile.
<img src="/images/9.19.png" alt="Getting started" />

3. export DOCKERID=<your docker id>
docker id = pijaru
<img src="/images/9.20.png" alt="Getting started" />

4. Echo the value of the variable back to the terminal to ensure it was stored correctly.
<img src="/images/9.21.png" alt="Getting started" />

5. Use the docker image build command to create a new Docker image using the instructions in the Dockerfile.
<img src="/images/9.22.png" alt="Getting started" />

6. Use the docker container run command to start a new container from the image you created.
<img src="/images/9.23.png" alt="Getting started" />

7. Click here to load the website which should be running.
<img src="/images/9.24.png" alt="Getting started" />

8. Once you’ve accessed your website, shut it down and remove it.
<img src="/images/9.25.png" alt="Getting started" />

### Task 3: Modify a running website

#### Start our web app with a bind mount

1. Let’s start the web app and mount the current directory into the container.
<img src="/images/9.26.png" alt="Getting started" />

2. The website should be running.
<img src="/images/9.27.png" alt="Getting started" />

## Modify the running website
1. Copy a new index.html into the container.
<img src="/images/9.28.png" alt="Getting started" />

2. Go to the running website and refresh the page. Notice that the site has changed.
<img src="/images/9.27.png" alt="Getting started" />

To show this, stop the current container and re-run the 1.0 image without a bind mount.
1. Stop and remove the currently running container.
<img src="/images/9.29.png" alt="Getting started" />

2. Rerun the current version without a bind mount.
<img src="/images/9.30.png" alt="Getting started" />

## Update the image
1. Build a new image and tag it as 2.0
<img src="/images/9.31.png" alt="Getting started" />

2. Let’s look at the images on the system
<img src="/images/9.32.png" alt="Getting started" />

## Test the new version
1. Run a new container from the new version of the image.
2. Check the new version of the website (You may need to refresh your browser to get the new version to load).
3. Run another new container, this time from the old version of the image.
4. View the old version of the website.

## Push your images to Docker Hub
1. List the images on your Docker host.
<img src="/images/9.33.png" alt="Getting started" />

2. Before you can push your images, you will need to log into Docker Hub.
<img src="/images/9.34.png" alt="Getting started" />

3. Push version 1.0 of your web app using docker image push.
<img src="/images/9.35.png" alt="Getting started" />

4. Now push version 2.0.
<img src="/images/9.36.png" alt="Getting started" />

5. https://hub.docker.com/r/pijaru/









