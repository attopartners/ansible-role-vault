# ansible-role-vault

[![Build Status](https://travis-ci.org/tkimball83/ansible-role-vault.svg?branch=master)](https://travis-ci.org/tkimball83/ansible-role-vault)

This role installs and enables HashiCorp's Vault on RHEL/CentOS.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    vault_backend:
      backend: consul
      address: 127.0.0.1:8500
      path: vault
    vault_listener:
      listener: tcp
      address: 127.0.0.1:8200
      tls_disable: True
    vault_telemetry:
      statsite_address: 127.0.0.1:8125
      disable_hostname: True

## Dependencies

 * https://galaxy.ansible.com/tkimball83/tkimball83/

## Example Playbook

    - hosts: servers
      roles:
        - role: tkimball83.vault
          vault_listener:
            listener: tcp
            address: "{{ ansible_default_ipv4.address }}:8200"
            tls_disable: True

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
