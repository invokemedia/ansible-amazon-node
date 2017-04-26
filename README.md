Ansible Amazon Linux Node
==================================

> Ansible scripts that setup Node.js for Amazon Linux AMIs

Requirements
------------

This role assumes you are using **AWS with an Amazon Linux AMI**.

This task does the following work:

* install nvm (node version manager)
* install node (whatever version you like)
* create handles for start and stopping node

Installation
------------

`git clone https://github.com/invokemedia/ansible-amazon-node roles/invokemedia.amazon-nodejs`

Role Variables
--------------

```
# the version of node you want to install/use
node_version: 7.9.0
# root for the app
app_root: /application
# the name of the service for the app
app_service_name: my-nodeapp
```

Tags
-----

* install-nvm - install and setup nvm
* install-node - install new version of node
* adddir - create a directory for the app
* addlog - create the log directory for the app

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
* `stop nodeapp` - stop your application

Because of the way the app runs in the background, these need to be run one after the other

License
-------

MIT

Author Information
------------------

* [Invoke](https://www.invokedigital.co/)
* <webmaster@invokedigital.co>

References
----------
