![](http://i.imgur.com/5QG0kVa.jpg?1)

# Ansible-Django
Ansible playbooks used to deploy a Django project on a remote server. This playbook assumes the remote server to be debian based. I used it to deploy [https://github.com/pattu777/LearningDjango](https://github.com/pattu777/LearningDjango) project on a Digital Ocean droplet. 

Also checkout my post [http://www.chinmayapatanaik.com/2016/06/25/Ansible-Django/](http://www.chinmayapatanaik.com/2016/06/25/Ansible-Django/) for more detailed description.

# Prerequisites

* Ansible installed on your local system.
* Passwordless setup for a user with sudo privilleges.
* A Django project copied onto the remote server. 
* For simplicity I am using SQLite as my back-end database.
* A custom domain pointing to your cloud server(Optional). This domain name is used while setting up Nginx.


# Tasks

* Install necessary packages.
  * System packages
  * Python packages
* Setup Django.
  * Create a virtualenv.
  * Install packages from requirements.txt file.
  * Create db models.
  * Collect static files.
* Setup Gunicorn.
  * Customize the conf file.
  * Copy the gunicorn.conf file to the remote server.
  * Restart gunicorn server.
* Setup Nginx.
  * Customize the Nginx conf file.
  * Copy the Nginx config file to the remote server.
  * Restart Nginx server.

# Developing

Clone the repo. Make sure the prerequisities are met. 

* Modify ansible.cfg.
* Provide IP address in hosts file.

Finally run the playbook as shown below.

```bash
$ git clone --recursive git@github.com:pattu777/Ansible-Django.git
$ cd Ansible-Django
$ ansible-playbook -s deploy.yml
```

# TODO
* A new role for setting up data stores like MySQL, Postgres etc.
* Check how to run the playbook in sudo mode through ansible.cfg 
* Clone a Git repository instead of assuming it's already present on the remote server

Finally go to your domain and see your django app working.
