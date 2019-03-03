---
layout: post
title: Django, Start a web app
---

As we will build a new project, the first step is to create a web app and start it.

With Django, it is a really simple step, really, like 3 command lines.
First, create a repository like "helloworld" :
```
mkdir helloworld
```
Once in this repository, we will use pipenv to create a virtual environment and install Django in it :
```
pipenv install Django==2.1.5
pipenv shell
```
Once in the environment shell, to create a new project, you can use a command line saying you want to start a new project and writing its name :
```
django-admin startproject hello_project .
```
The "." at the end represent relative path where you want to install your project. In our case "." means here, the repository we are in.
If we look at what is now in our "helloworld" repository, we can see the Pipfile and Pipfile.lock (because we used pipenv), and a new repository "hello_project". In this one, we have different files created by Django. The "settings.py", "urls.py", "wsgi.py" and "manage.py". We will use the three first file in future steps to create our web app. But for now we can start a local server with this empty project, by using the last file : "manage.py", by running :
```
python manage.py runserver
```
By going to your localhost on the 8000 port, on the following url : "http://localhost:8000/", you will see a Django page saying it was installed sucessfully.
