# ansible-role-vault

[![Build Status](https://travis-ci.org/tkimball83/ansible-role-vault.svg?branch=master)](https://travis-ci.org/tkimball83/ansible-role-vault)

This role installs and enables HashiCorp's vault on RHEL/CentOS.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    vault_backend_address: "127.0.0.1:8500"
    vault_backend_path: "vault"
    vault_listener_address: "127.0.0.1:8200"
    vault_listener_tls_disable: True
    vault_telemetry_enable: True
    vault_telemetry_disable_hostname: True
    vault_telemetry_statsite_address: "127.0.0.1:8125"

## Dependencies

 * https://galaxy.ansible.com/tkimball83/tkimball83/

## Example Playbook

    - hosts: servers
      roles:
        - role: tkimball83.vault
          vault_listener_address: "{{ ansible_default_ipv4.address }}:8200"
          vault_listener_tls_disable: True
         
## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
