Ansible Laravel Homestead Settler
==================================

> Ansible scripts that setup Node.js and create an app in Upstart for Amazon Linux AMIs

Requirements
------------

This role assumes you are using **AWS with an Amazon Linux AMI**.

This task does the following work:

* install nvm (node version manager)
* install node (whatever version you like)
* create a user for node
* create an entry in Upstart to start, stop, restart, and respawn your app

Installation
------------

`git clone https://github.com/invokemedia/ansible-amazon-node roles/invokemedia.amazon-nodejs`

Role Variables
--------------

```
# the version of node you want to install/use
node_version: 7.9
# the name of the application
app_name: Project Laura Queue Worker
# the system user for this application
app_user: nodeapp
# root for the app, relative to the app_user home directory
app_root: /application
# who made this application?
app_author: Invoke
# the name of the service for the app
app_service_name: my-nodeapp
```

Tags
-----

* install-nvm - install and setup nvm
* install-node - install new version of node
* adduser - create a node specific user
* addlog - create the upstart log directory for the app
* addupstart - create the upstart entry for the app

Dependencies
------------

None.

Example Playbook
-------------------------

Here is how you would launch the default Nginx setup.

```
- hosts: web
  sudo: yes
  vars:
  roles:
    - { role: invokemedia.amazon-nodejs }
```

Handlers
--------

* `start nodeapp` - start your application
* `restart nodeapp` - restart your application
* `stop nodeapp` - stop your application

License
-------

MIT

Author Information
------------------

* [Invoke](https://www.invokedigital.co/)
* <webmaster@invokedigital.co>

References
----------
