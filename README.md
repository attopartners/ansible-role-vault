# ansible-role-vault

[![Build Status](https://travis-ci.org/tkimball83/ansible-role-vault.svg?branch=master)](https://travis-ci.org/tkimball83/ansible-role-vault)

This role installs and enables HashiCorp's vault on RHEL/CentOS.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    vault_backend_address: 127.0.0.1:8500
    vault_backend_path: vault"
    vault_listener_address: 127.0.0.1:8200
    vault_listener_tls_disable: True
    vault_telemetry_enable: True
    vault_telemetry_disable_hostname: True
    vault_telemetry_statsite_address: 127.0.0.1:8125

Additional variables available, not defined by default:

    vault_bin: /usr/sbin/vault
    vault_backend_scheme: https
    vault_backend_token: xxxxxx
    vault_backend_max_parallel: 128
    vault_backend_tls_skip_verify: False
    vault_backend_tls_ca_file: /path/to/ca/file
    vault_backend_tls_cert_file: /path/to/cert/file
    vault_backend_tls_key_file: /path/to/key/file
    vault_config_path: /etc/vault/vault.hcl
    vault_listener_tls_cert_file: /path/to/cert/file
    vault_listener_tls_key_file: /path/to/key/file
    vault_listener_tls_min_version: tls12
    vault_log_file: /var/log/vault.log
    vault_log_level: info
    vault_pid_file: /var/run/vault.pid

## Dependencies

 * https://galaxy.ansible.com/tkimball83/tkimball83/

## Example Playbook

    - hosts: servers
      roles:
        - role: tkimball83.vault
          vault_listener_address: "{{ ansible_default_ipv4.address }}:8200"
          vault_listener_tls_disable: False

## Partners

[![packagecloud](http://dka575ofm4ao0.cloudfront.net/pages-transactional_logos/retina/10543/gKme3F4XRaC5EyKJzKsA)](https://packagecloud.io)

Do you need trustworthy hosted package repositories?  Then packagecloud is for you.

A big thank you to packagecloud for supporting the open source community!
         
## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
