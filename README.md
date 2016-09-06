rsyslog
=======

This role installs and configures [rsyslog](http://www.rsyslog.com/).

Role Variables
--------------

- `rsyslog_init_system`: OS init system. Docker phusion/baseimage uses 'runit'. (default 'upstart')
- `rsyslog_confs`: List of custom confs to enable (default: empty list)

Example Playbook
----------------

    - hosts: servers
      roles:
        - {
          role: rsyslog,
          rsyslog_init_system: 'runit'
        }

License
-------

MIT

[![Build Status](https://travis-ci.org/dpujadas/ansible-role-rsyslog.svg?branch=master)](https://travis-ci.org/dpujadas/ansible-role-rsyslog)