==============
ansible-mopidy
==============

.. image:: http://img.shields.io/badge/ansible--galaxy-mopidy-blue.svg
  :target: https://galaxy.ansible.com/narfman0/mopidy/

.. image:: https://travis-ci.org/narfman0/ansible-mopidy.png?branch=master
    :target: https://travis-ci.org/narfman0/ansible-mopidy

Ansible role that installs Mopidy_ on Ubuntu/Debian. Thanks to
Daniel White for the inspiration :)

.. _mopidy: https://www.mopidy.com/

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`)

A list of package manager extensions::

    mopidy_packages:
      - mopidy-spotify
      - mopidy-pandora

A list of pip extensions::

    mopidy_pip: []

A list of additional options to configure. Each item requires the `section`, `option` and `value` properties
to be defined. These are used by the ini_file_ module to configure `/etc/mopidy/mopidy.conf`::

    mopidy_settings: []

.. _ini_file: http://docs.ansible.com/ansible/ini_file_module.html

Example
-------

playbook.yml::

    - hosts: mopidy-hosts
      roles:
        - role: mopidy

Testing
-------

A vagrant file has been included for easy testing. To get a running mopidy::

    vagrant up --provider virtualbox

License
-------

Please see included LICENSE file for license specifics

Copyright 2017 Jon Robison
