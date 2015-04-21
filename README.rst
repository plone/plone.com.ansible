plone_comServer Ansible Playbooks
========================

Ansible playbooks meant to be sufficient to build or rebuild a server with minimal preparation.

These do not handle live data transfer.

Prerequisites
-------------

Ubuntu 14.04 server and an ssh login with full sudo.

Typical use::

    ansible-playbook -i plone_com_host -K firewall.yml
    ansible-playbook -i plone_com_host -K add_users.yml
    ansible-playbook -i plone_com_host -K server_config.yml
    ansible-playbook -i plone_com_host -K cron_jobs.yml

Playbooks
---------

firewall.yml
~~~~~~~~~~~~

Closes all ports except 80, 443, Munin. Uses ufw.

add_users.yml
~~~~~~~~~~~~~

Establishes basic user set

server_config.yml
~~~~~~~~~~~~~~~~~

The real worker: Installs required packages, sets up:

* Postfix, including aliases
* Plone live and staging servers
* supervisor
* haproxy
* varnish
* nginx
* munin-node

This playbook does *NOT* run buildout. Log in and do that separately.

cron_jobs.yml
~~~~~~~~~~~~~

All the cron jobs.
