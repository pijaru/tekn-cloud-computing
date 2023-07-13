#  Docker Compose untuk App Containerization and Orchestration

<img src="/images/11.1.png" alt="Getting started" />

##  Stage Setup
Let’s get started by first cloning the demo code repository, changing the working directory, and checking the demo branch out.
<img src="/images/11.2.png" alt="Getting started" />

## Step 0: Basic Link Extractor Script
<img src="/images/11.3.png" alt="Getting started" />

The linkextractor.py file is the interesting one here, so let’s look at its contents:
cat linkextractor.py
<img src="/images/11.4.png" alt="Getting started" />

This is a simple Python script that imports three packages: sys from the standard library and two popular third-party packages requests and bs4. User-supplied command line argument (which is expected to be a URL to an HTML page) is used to fetch the page using the requests package, then parsed using the BeautifulSoup. The parsed object is then iterated over to find all the anchor elements (i.e., <a> tags) and print the value of their href attribute that contains the hyperlink.

However, this seemingly simple script might not be the easiest one to run on a machine that does not meet its requirements. The README.md file suggests how to run it, so let’s give it a try:
<img src="/images/11.5.png" alt="Getting started" />

When we tried to execute it as a script, we got the Permission denied error. Let’s check the current permissions on this file:
ls -l linkextractor.py
<img src="/images/11.6.png" alt="Getting started" />

This current permission -rw-r--r-- indicates that the script is not set to be executable. We can either change it by running chmod a+x linkextractor.py or run it as a Python program instead of a self-executing script as illustrated below:
python3 linkextractor.py
<img src="/images/11.7.png" alt="Getting started" />

Here we got the first ImportError message because we are missing the third-party package needed by the script. We can install that Python package (and potentially other missing packages) using one of the many techniques to make it work, but it is too much work for such a simple script, which might not be obvious for those who are not familiar with Python’s ecosystem.

Depending on which machine and operating system you are trying to run this script on, what software is already installed, and how much access you have, you might face some of these potential difficulties:

Is the script executable?
Is Python installed on the machine?
Can you install software on the machine?
Is pip installed?
Are requests and beautifulsoup4 Python libraries installed?
This is where application containerization tools like Docker come in handy. In the next step we will try to containerize this script and make it easier to execute.

## Step 1: Containerized Link Extractor Script
Checkout the step1 branch and list files in it.
We have added one new file (i.e., Dockerfile) in this step. Let’s look into its contents:
Using this Dockerfile we can prepare a Docker image for this script. We start from the official python Docker image that contains Python’s run-time environment as well as necessary tools to install Python packages and dependencies. We then add some metadata as labels (this step is not essential, but is a good practice nonetheless). Next two instructions run the pip install command to install the two third-party packages needed for the script to function properly. We then create a working directory /app, copy the linkextractor.py file in it, and change its permissions to make it an executable script. Finally, we set the script as the entrypoint for the image.

So far, we have just described how we want our Docker image to be like, but didn’t really build one. So let’s do just that:
<img src="/images/11.8.png" alt="Getting started" />

We have created a Docker image named linkextractor:step1 based on the Dockerfile illustrated above. If the build was successful, we should be able to see it in the list of image:
<img src="/images/11.9.png" alt="Getting started" />

This image should have all the necessary ingredients packaged in it to run the script anywhere on a machine that supports Docker. Now, let’s run a one-off container with this image and extract links from some live web pages:

This outputs a single link that is present in the simple example.com web page:
<img src="/images/11.10.png" alt="Getting started" />





