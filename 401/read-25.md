# Django REST Framework & Docker

## A Beginner's Guide to Docker

With Docker it doesn’t matter if you are using a Mac, Windows, or Linux computer anymore. The entire development environment is isolated: programming language, software packages, databases, and more.

With Docker we now longer have to mess around with virtual environments. We can faithfully reproduce a production environment locally. And Docker can be shared among team members so everyone is working on the same setup. Wins all around.

### Linux Containers 

Docker is really just Linux containers which are a type of virtualization.

Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. How could multiple programmers use the same single machine? The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.

If you rent space on a cloud provider like AWS they are typically not providing you with a dedicated piece of hardware. Instead you are probably sharing a physical server with hundreds or even thousands of other clients.

What’s the downside to a virtual machine? Size and speed. A typical guest operating system can easily take up 700MB of size. So if one physical server supports three virtual machines, that’s at least 2.1GB of disk space taken up along with separate needs for CPU and memory resources.

### Containers vs Virtual Environments

If you are a Python programmer (like me) a common question at this point is, what about virtual environments? How do they differ from containers?

Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. Virtual environments are great.

But…virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version. So when we use Python 2.7 in a project, we’re pointing to an installation of Python 2.7 on the computer itself, not actually within the virtual environment.

Also we can’t run a production database or other services within virtual environments so compared to Docker containers they are far more limited.

### Install Docker

Ok, enough theory. Let’s start using Docker before we explore further concepts.

To install Docker we need to download the desktop app on our computer and create a free account. The initial download of Docker might take some time to download. It’s a big file. Feel free to stretch your legs at this point!

Once Docker is done installing we can confirm the correct version is running. It should be at least version 19.

```
$ docker --version
Docker version 19.03.5, build 633a0ea
```

Docker Compose is an additional tool that is automatically included with Mac and Windows downloads of Docker. However if you are on Linux, you will need to add it manually. You can do this by running the command sudo pip install docker-compose after your Docker installation is complete.

Now run the command below to confirm you have a working version of it, too. The version should be at least 1.24.x.

```
$ docker-compose --version
docker-compose version 1.24.1, build 4667896b
```

### Hello, World

To confirm Docker installed correctly we can run our first command docker run hello-world. This will download an official image and then run the container. We’ll discuss both images and containers shortly.

```
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:9572f7cdcee8591948c2963463447a53466950b3fc15a247fcad1917ca215a2f
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

A good command to inspect Docker is docker info which we can run now. It will contain a lot of output but focus on the top lines which show we now have 1 container which is stopped and 1 image.

```
$ docker info
Containers: 1
 Running: 0
 Paused: 0
 Stopped: 1
Images: 1
```

Want to inspect just the current image?

```
$ docker image ls
REPOSITORY          TAG        IMAGE ID            CREATED             SIZE
hello-world         latest     fce289e99eb9        12 months ago       1.84kB
```

There is the hello-world image which we just downloaded. How about inspecting containers, either running, paused, or stopped?

```
$ docker container ls -la
CONTAINER ID IMAGE        COMMAND   CREATED  STATUS     PORTS  NAMES
c827847463a1 hello-world  "/hello"  About... Exited (0)        blissful_swartz

```

I have shortened the actual about for CREATED and STATUS to fit but we can see the container for hello-world. The NAMES here, musing_raman, is randomly created by Docker unless we specifically set it so your name will likely be different.

Also, why do we need ls -la here instead of ls? The answer is because the container is stopped! Only running containers will appear with docker container ls.

### Images and Containers

Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.

When we ran hello-world we used an official Docker image. We did not have to create the image ourself. But typically we will create custom images and we do so using a Dockerfile. We also will use docker-compose.yml files to run the containers.

A baking analogy we can use here is as follows:

A Dockerfile is the recipe for a cake
An image is a snapshot of the recipe at a given time
A docker-compose.yml says how to make the cake
And the container is the actual, baked cake
There are a large number of official images available on Docker Hub for common software like different flavors of Linux, programming languages, and so on. For example, the Hello World image is there.

## Library Website and API

Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework; it always must be added to a project after Django itself has been installed and configured.

In this chapter we will review the similarities and differences between traditional Django and Django REST Framework. The most important takeaway is that Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON.

To illustrate these concepts, we will build out a basic Library website with traditional Django and then extend it into a web API with Django REST Framework.

Make sure you already have Python 3 and Pipenv installed on your computer. Complete instructions can be found here if you need help.

### Traditional Django

First we need a dedicated directory on our computer to store the code. This can live anywhere but for convenience, if you are on a Mac, we can place it in the Desktop folder. The location really does not matter; it just needs to be easily accessible.

```
$ cd ~/Desktop
$ mkdir code && cd code
```
Now we are within the code folder which will be the location for all the code in this book. The next step is to create a dedicated directory for our library site, install Django via Pipenv, and then enter the virtual environment using the shell command. You should always use a dedicated virtual environment for every new Python project.

```
$ mkdir library && cd library
$ pipenv install django~=3.1.0
$ pipenv shell
(library) $
```
Pipenv creates a Pipfile and a Pipfile.lock within our current directory. The (library) in parentheses before the command line shows that our virtual environment is active.

A traditional Django website consists of a single project and one (or more) apps representing discrete functionality. Let’s create a new project with the startproject command. Don’t forget to include the period . at the end which installs the code in our current directory. If you do not include the period, Django will create an additional directory by default.

```
(library) $ django-admin startproject config .

```

Django automatically generates a new project for us which we can see with the tree command. (Note: If tree doesn’t work for you on a Mac, install it with Homebrew: brew install tree.)

```
(library) $ tree
.
├── Pipfile
├── Pipfile.lock
├── config
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
```

The files have the following roles:

__init__.py is a Python way to treat a directory as a package; it is empty
asgi.py stands for Asynchronous Server Gateway Interface and is a new option in Django 3.0+
settings.py contains all the configuration for our project
urls.py controls the top-level URL routes
wsgi.py stands for Web Server Gateway Interface and helps Django serve the eventual web pages
manage.py executes various Django commands such as running the local web server or creating a new app.

Run migrate to sync the database with Django’s default settings and start up the local Django web server.

(library) $ python manage.py migrate
(library) $ python manage.py runserver

Open a web browser to http://127.0.0.1:8000/ to confirm our project is successfully installed.

[image](https://djangoforapis.com/assets/images/00_welcome31.png)

### First app

The typical next step is to start adding apps, which represent discrete areas of functionality. A single Django project can support multiple apps.

Stop the local server by typing Control + c and then create a books app.

```
(library) $ python manage.py startapp books
```

Now let’s see what files Django has generated.

```
(library) $ tree
.
├── Pipfile
├── Pipfile.lock
├── books
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py   
|   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── config
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
```

Each app has a __init__.py file identifying it as a Python package. There are 6 new files created:

admin.py is a configuration file for the built-in Django Admin app
apps.py is a configuration file for the app itself
the migrations/ directory stores migrations files for database changes
models.py is where we define our database models
tests.py is for our app-specific tests
views.py is where we handle the request/response logic for our web app

Typically developers will also create an urls.py file within each app too for routing.

Let’s build out the files so that our Library project lists out all books on the homepage. Open the text editor of your choice to the config/settings.py file. The first step is to add the new app to our INSTALLED_APPS configuration. You’ll often see new apps added at the bottom but since Django loads apps in order, the newer best practice is to place local apps like books at the top instead.

```
# library_project/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # Local
    'books', # new
]
```

Then run migrate to sync our database with the changes.

```
(library) $ python manage.py migrate
```

Each web page in traditional Django requires several files: a view, url, and template. But first we need a database model so let’s start there.

