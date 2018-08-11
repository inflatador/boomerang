# django_blank
Using vagrant and ansible, these files will setup Django 2.01 with a MariaDB database on Debian 9. Vagrant uses ansible-local provisioning to  run the playbook.yml file on the vm.

Requirements: Vagrant

The playbook will set the database name, username, and password to the same value. To change the value of the database, username, and password, edit the vagrant file and change 'django' to a value of your choosing.   

```
ansible.extra_vars = {  
        dbname: 'django'  
      }
```

// Installation  
git clone git@github.com:txhc4life/django_blank.git  
cd django_blank  
vagrant up  

// Once finished you can then ssh into the instance and create project. Replace mysite with your project's name.  
vagran ssh   
/home/vagrant/.local/bin/django-admin startproject mysite  
cd mysite  

// You can now set the database setting in the mysite/settings.py file.  
vi mysite/settings.py

```  
DATABASES = {
    'default': {  
        'ENGINE': 'django.db.backends.mysql',  
        'NAME': 'django',  
        'USER': 'django',  
        'PASSWORD': 'django',  
        'HOST': '127.0.0.1',  
        'PORT': '3306',  
    }  
} 
``` 

// Now you can start the development web server.  
python3 manage.py runserver 0:8000    

// Test development server from host.  
curl 127.0.0.1:8000  
