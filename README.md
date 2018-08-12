# django_blank
Using Vagrant, Virtualbox and Ansible, these files will setup Django 2.01 with a MariaDB database on Debian 9. After following the installation instructions the user with have a development environment ready to start the Django tutorial at https://docs.djangoproject.com/en/2.1/intro/tutorial01/

Requirements: Vagrant and Virtualbox

The playbook will set the database name, django project, username, and password to the same value. To change the value, edit the vagrant file and change 'mysite' to a value of your choosing.   

```
ansible.extra_vars = {  
        dbname: 'mysite'  
      }
```

// Installation  
git clone git@github.com:txhc4life/django_blank.git  
cd django_blank  
vagrant up  

// Once finished you can then ssh into the instance and create project. Replace mysite with your project's name.  
vagran ssh   
cd mysite  

// You can now set the database setting in the mysite/settings.py file.  
vim mysite/settings.py

```  
DATABASES = {
    'default': {  
        'ENGINE': 'django.db.backends.mysql',  
        'NAME': 'mysite',  
        'USER': 'mysite',  
        'PASSWORD': 'mysite',  
        'HOST': '127.0.0.1',  
        'PORT': '3306',  
    }  
}
```

// Now you can start the development web server.  
python3 manage.py runserver 0:8000    

// Test development server from host.  
curl 127.0.0.1:8000  
