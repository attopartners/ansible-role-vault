# ansible-role-vault

[![Build Status](https://travis-ci.org/tkimball83/ansible-role-vault.svg?branch=master)](https://travis-ci.org/tkimball83/ansible-role-vault)

This role installs and enables HashiCorp's vault on RHEL/CentOS.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    vault_backend:
      type: consul
      options:
        address: 127.0.0.1:8500
        path: vault
    vault_listener:
      type: tcp
      options:
        address: 127.0.0.1:8200
        tls_disable: '1'
    vault_telemetry:
      statsite_address: 127.0.0.1:8125
      disable_hostname: 'true'

Adding additional options is easy as the template simply iterates
though the key/value pairs that you set.  You can add additional
options by following this example:

    vault_backend:
      type: consul
      options:
        address: 127.0.0.1:8500
        path: vault
        scheme: https
        max_parallel: 128
        tls_skip_verify: 'true'
    vault_listener:
      type: tcp
      options:
        address: 127.0.0.1:8200
        tls_cert_file: /path/to/cert/file
        tls_key_file: /path/to/key/file
        tls_min_version: tls10 
        tls_disable: '0'
    vault_telemetry:
      statsite_address: 127.0.0.1:8125
      statsd_address: 127.0.0.1:31337
      disable_hostname: 'true'

## Dependencies

 * https://galaxy.ansible.com/tkimball83/tkimball83/

## Example Playbook

    - hosts: servers
      roles:
        - role: tkimball83.vault
          vault_listener:
            type: tcp
            options:
              address: "{{ ansible_default_ipv4.address }}:8200"
              tls_disable: '1'

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
