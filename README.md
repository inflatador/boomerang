# django_blank
Using vagrant and ansible, these files will setup Django 2.01 with a MariaDB database on Debian 9. Vagrant uses ansible-local provisioning to  run the playbook.yml file on the vm. 

Requirements: Vagrant

The playbook will set the database name, username, and password to the same value. To change the value of the database, username, and password, edit the vagrant file and change 'django' to a value of your choosing.   

ansible.extra_vars = {  
        dbname: 'django'  
      }

// Installation  
git clone git@github.com:txhc4life/django_blank.git  
cd django_blank  
vagrant up  

// Once finished you can then ssh into the instance, create project, and start the development server.  Replace mysite with your project's name.  
vagran ssh   
cd /vagrant
/home/vagrant/.local/bin/django-admin startproject mysite  
cd mysite  
python3 manage.py runserver 0:8000    

// Test development server from host.
curl 127.0.0.1:8000  


