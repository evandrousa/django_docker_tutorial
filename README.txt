=====
Urna Portable WebApp with Django and Dockers (Urna=Poll in portuguese)
=====

Description 
-----------
Project generated while following 2 tutorial online: 
"https://docs.docker.com/compose/django/" - https://docs.docker.com/compose/django/
"Writing your first Django app" - https://docs.djangoproject.com/en/1.10/intro/tutorial01/.

The goal was to learn how to make a portable web application on my PC that would easily be transfered to an emberded linux device(Raspberry Pi). 

Tutorial was performed by me, Evandro Gomes on 11/27/2016. 
Yes, I was bored at home during the 4 days Thanksgiving break =)


Content 
-----------
There are 3 files responsible for the Docker portion of the project
"docker_compose.yml" - used to deploy 2 containers: web(from local file) and db(from remote image)
"Dockerfile" - the docker file used to create the web container
"requirements.txt" - list dependencies for pip to install in the web container when it is deployed
All others are Django files and are supposed to be used/executed by the containers
"site_do_projeto" -the Django project created from the containerin order to make the webapp
"urna" - the folder containing a simple Django WebApp to conduct Web-based polls.  


Pre-requesit
-----------
Docker-engine
Docker-compose


Quick start
-----------
1. Open a terminal window and change directory into this directory
2. Deploy the containers with command 
	$ docker-compose up
3. Open your browser and navigate to the polls website
	http://localhost:8000/urna/
4. Visit the admin page as well! Credentials are user: root pass: Brasil123
	http://localhost:8000/admin/ 


Executing commands inside the container
-----------
You will find a need to send commands to Django's manage.py inside the container 
This can be done via the docker-compose tool
1. Open a second terminal window
2. Execute cmd in container with the following cmd sctructure
	$ docker-compose run "container_name" "command" 
	example to migrate Database
		docker-compose run web python manage.py migrate
	example to start Django's shell
		docker-compose run web python manage.py shell


System Info
-----------
Information about the machine and tools used to develop all of this.
All dependencies required to run the app are not listed because they live inside the containers
$uname -a	
	Linux user 4.4.0-47-generic #68~14.04.1-Ubuntu SMP x86_64 x86_64 x86_64 GNU/Linux
$ docker version
	 Version:      1.12.3
	 API version:  1.24
	 Go version:   go1.6.3
	 Git commit:   6b644ec
	 OS/Arch:      linux/amd64
$ docker-compose version
	docker-compose version 1.8.1, build 878cff1
	docker-py version: 1.10.3
	CPython version: 2.7.9
	OpenSSL version: OpenSSL 1.0.1e 11 Feb 2013
