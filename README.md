PERSONAL BLOG - ANSIBLE
===

This is the ansible suit to deploy an instance of the blog application I created (https://github.com/Lohit13/PersonalBlog).
Deployment is via uWSGI as the server and Nginx as the reverse proxy. The environment is contained within a virtualenv.

Approx. time taken: 3.5 min

REQUIREMENTS
===

We only need ansible to be installed the machine. Refer: http://docs.ansible.com/intro_installation.html

On Ubuntu, it is as follows:

- sudo apt-get install software-properties-common
- sudo apt-add-repository ppa:ansible/ansible
- sudo apt-get update
- sudo apt-get install ansible

USAGE
===

1. Open deploy.yml. Fill in the SSH username in the two required places.
2. cd into ./files directory
3. Open exec, site_nginx.conf and site_uwsgi.conf and REPLACE all {{user}} with the ssh username you filled in step 1.
4. In site_nginx.conf, replace {{fqdn}} with the IP or FQDN of the server.
5. Open hosts file in the root directory, append the IP address of the server.
6. Finally, open terminal, cd to directory and execute: ansible-playbook --ask-pass --ask-sudo-pass deploy.yml -i hosts
7. Provide the SSH and sudo user password when prompted.
8. Dance in joy!

AUTHORS
===

Lohitaksh Parmar 
