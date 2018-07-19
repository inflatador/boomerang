# django_blank
Using vagrant and ansible these files will setup Django 2.01 with a MariaDB database.

Requirements: Vagrant

git clone git@github.com:txhc4life/django_blank.git  
cd django_blank
vagrant up

// Once finished you can then ssh into the instance, create project, and start the development server.
vagran ssh 
django-admin startproject mysite
cd mysite
python manage.py runserver 0:8000
exit

// Test development server
curl 127.0.0.1:8000
