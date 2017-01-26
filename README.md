rsyslog
=======

This role installs and configures [rsyslog](http://www.rsyslog.com/).

Role Variables
--------------

- `rsyslog_init_system`: OS init system. Docker phusion/baseimage uses 'runit'. (default 'upstart')
- `rsyslog_allow_udp`:  Allow UDP syslog reception (default: False)
- `rsyslog_udp_port`: UPD port for syslog reception (default: '514')
- `rsyslog_allow_tcp`:  Allow TCP syslog reception (default: False)
- `rsyslog_udp_port`: TCD port for syslog reception (default: '514')
- `rsyslog_confs`: List of custom confs to enable (default: empty list)
- `rsyslog_modules_install`: List of modules to install (default: empty list)
- `rsyslog_modules_enabled`: List of modules to enable (default: empty list)

Example Playbook
----------------

    - hosts: servers
      vars:
        rsyslog_modules_install:
          - elasticsearch
        rsyslog_modules_enabled:
          - omelasticsearch
      roles:
        - {
          role: rsyslog,
          rsyslog_init_system: 'runit',
          rsyslog_allow_tcp: True
        }

License
-------

MIT

[![Build Status](https://travis-ci.org/dpujadas/ansible-role-rsyslog.svg?branch=master)](https://travis-ci.org/dpujadas/ansible-role-rsyslog)