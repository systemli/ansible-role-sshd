ansible-sshd
============

Role to install & maintain the OpenSSH Daemon

Role Variables
--------------

The playbook requires no special configuration, but offers a bunch of options.

Defaults:

    sshd_apt_backports_url: "http://ftp.de.debian.org/debian/"
    sshd_apt_backports_distribution: "{{ ansible_distribution_release }}-backports"
    
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
    sshd_ignore_rhosts: "yes"
    sshd_rhosts_rsa_authentication: "no"
    sshd_hostbased_authentication: "no"
    sshd_permit_empty_passwords: "no"
    sshd_challenge_response_authentication: "no"
    sshd_x11_forwarding: "yes"
    sshd_x11_display_offset: 10
    sshd_print_motd: "no"
    sshd_print_last_log: "yes"
    sshd_tcp_keep_alive: "yes"
    sshd_client_alive_interval: 3600
    sshd_client_alive_count_max: 0
    sshd_use_pam: "yes"
    sshd_use_dns: "no"
    sshd_sftp_chroot: "no"
    sshd_sftp_chroot_group: sftoonly


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: 0x46616c6b.sshd }

License
-------

GPLv3
