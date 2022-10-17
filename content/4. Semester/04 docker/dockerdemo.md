---
bookCollapseSection: true
weight: 20
---

# Create your fist Docker application
The purpose of this Docker application is to create a Python program that print/displays a sentence. 

The Python program will have to be launched through Dockerfile.

Note: You must have install Docker on your computer

## Create the application
You have to create a folder on your computer - minfirstdockerapp

It must contain the following two files:

- **main.py** - *Python file containing the code to be executed*
- **Dockerfile** - *Docker file that will contain the necessary instructions to create the environment*

### main.py
The main.py file is very simpel for this demo

```python
print("Welcome to your first Docker app")
```

### Dockerfile
The purpose of this Docker file is to run your Python code.

To do this, your Docker must contain all the dependencies necessary to launch Python. A Linux (*Ubuntu*) with Python installed on it should do the trick.

First step in creating the Dockerfile is to access the DockerHub website - [hub.docker.com](https://hub.docker.com)

The DockerHub website contains many pre-designed images you can use. For this case, type **Python** in the search bar. 

![](./_image/python_dockerhub.jpg)

The first result is the official image to execute Python.

You must create a Dockerfile and add this commands:

```dockerfile
# Importing the base image.
FROM python:latest

# To launch your python code, you must import it into our image.
# Use the keyword 'COPY' to do that.
# The first parameter 'main.py' is the name of the file on the host.
# The second parameter '/' is the path where to put the file on the image.
COPY main.py /

# You need to define the command to launch when you run the image.
# Use the keyword 'CMD' to do that.
CMD [ "python", "./main.py" ]
```

Remember that the Dockerfile doesn't have a file extension

## Run the application
The launce of your application are done in 2 parts

### Build
    docker build -t python-demo . 

![](./_image/docker%20build.jpg)

### Launch
    docker run python-demo

![](./_image/docker-run-first.jpg)