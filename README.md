# django_blank
Using Vagrant, Virtualbox and Ansible, these files will setup Django 2.01 with a MariaDB database on Debian 9. After following the installation instructions, the user will have a development environment ready to start their own Django project.

Learn more about Django here: https://www.djangoproject.com/

Requirements: Vagrant and Virtualbox

The playbook will set the django project, database name, database username, and database password to the same value. The default value is 'mysite'. To change the value, edit the Vagrant file and change 'mysite' to a value of your choosing.   

```
ansible.extra_vars = {  
        dbname: 'mysite'  
      }
```

// Installation  
git clone git@github.com:txhc4life/django_blank.git  
cd django_blank  
vagrant up  

// Once finished you can then ssh into the vm.   
vagrant ssh   

// Change to the django project's directory. Replace 'mysite' with your project's name.  
cd mysite  

// Now you can start the development web server.  
python3 manage.py runserver 0:8000    

// Test development server from host.  
curl 127.0.0.1:8000  
