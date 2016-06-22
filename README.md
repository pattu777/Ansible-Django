# Ansible-Django
Ansible playbooks used to deploy [https://github.com/pattu777/LearningDjango](https://github.com/pattu777/LearningDjango) project on a remote Ubuntu server.

### Tasks

* Install necessary packages.
  * System packages
  * Python packages
* Setup Django.
  * Create a virtualenv
  * Install packages from requirements.txt
  * Create models.
  * Collect static files.
* Setup Gunicorn.
  * Customize the conf file.
  * Copy the gunicorn.conf file to the remote server.
  * Restart gunicorn server.
* Setup Nginx.
  * Customize the nginx conf file.
  * Copy the nginx config file to the remote server.
  * Restart nginx server.

### Prerequisites

* Ansible installed on your local system.
* Passwordless setup for a user with sudo privilleges.
* Our Django project copied onto the remote server. 
* A custom domain pointing to your cloud server.

### Developing

Clone the repo. Make sure the prerequisities are met. 

* Modify ansible.cfg.
* Provide IP address in hosts file.

Finally run the playbook as shown below.

```bash
$ git clone --recursive git@github.com:pattu777/Ansible-Django.git
$ cd Ansible-Django
$ ansible-playbook -s deploy.yml
```

### TODO
* Check how to run the playbook in sudo mode through ansible.cfg 
* Clone a Git repository instead of assuming it's already present on the remote server

Finally go to your domain and see your django app working.
