ansible-sshd
============

[![Build Status](https://travis-ci.org/systemli/ansible-sshd.svg)](https://travis-ci.org/systemli/ansible-sshd) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-sshd-blue.svg)](https://galaxy.ansible.com/systemli/sshd/)

Role to install & maintain the OpenSSH Daemon

Role Variables
--------------

The playbook requires no special configuration, but offers a bunch of options.

Defaults:

    sshd_port: 22
    sshd_listen_address: 0.0.0.0
    sshd_syslog_facility: AUTH
    sshd_log_level: INFO
    sshd_use_privilege_seperation: "yes"
    sshd_key_regeneration_interval: 3600
    sshd_server_key_bits: 1024
    sshd_login_grace_time: 120
    sshd_permit_root_login: "no"
    sshd_strict_modes: "yes"
    sshd_rsa_authentication: "yes"
    sshd_pubkey_authentication: "yes"
    sshd_authorized_keys_file: "%h/.ssh/authorized_keys"
    sshd_password_authentication: "no"
    sshd_allow_users: []
    sshd_allow_groups: []
    sshd_ignore_rhosts: "yes"
    sshd_rhosts_rsa_authentication: "no"
    sshd_hostbased_authentication: "no"
    sshd_permit_empty_passwords: "no"
    sshd_challenge_response_authentication: "no"
    sshd_x11_forwarding: "no"
    sshd_x11_display_offset: 10
    sshd_print_motd: "no"
    sshd_print_last_log: "yes"
    sshd_tcp_keep_alive: "yes"
    sshd_max_startups: "10:30:60"
    sshd_client_alive_interval: 3600
    sshd_client_alive_count_max: 0
    sshd_use_pam: "yes"
    sshd_use_dns: "no"
    sshd_sftp_chroot: "no"
    sshd_sftp_chroot_group: sftponly

Download
--------

Download latest release with `ansible-galaxy`

	ansible-galaxy install systemli.sshd


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: systemli.sshd }

Testing & Development
---------------------

For developing and testing the role we use Travis CI and Vagrant. On the local environment you can easily test the role with

```
vagrant up trusty
# other available releases are precise, wheezy and jessie
```

License
-------

GPLv3

Author Information
------------------

https://www.systemli.org