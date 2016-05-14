# ansible-role-vault

[![Build Status](https://travis-ci.org/tkimball83/ansible-role-vault.svg?branch=master)](https://travis-ci.org/tkimball83/ansible-role-vault)

This role installs and enables HashiCorp's vault on RHEL/CentOS.

## Requirements

This role requies a storage backend.  By default it's configured to use consul but supports all storage backends.  Simply
update the hash with the correct options for your backend.

If you're interested in a role for consul it can be found here:

 *  * https://galaxy.ansible.com/tkimball83/tkimball83/

## Role Variables

Available variables are listed below, along with default values:

    vault_backend:
      address: 127.0.0.1:8500
      path: vault
      storage: consul
    vault_listener:
      address: 127.0.0.1:8200
      tls_disable: '1'

Additional variables available, not defined by default:

    vault_bin: /usr/sbin/vault
    vault_backend:
      address: 127.0.0.1:8500
      max_parallel: 128
      path: vault
      scheme: https
      storage: consul
      token: xxxxxxxxxx
      tls_ca_file: /path/to/ca/file
      tls_cert_file: /path/to/cert/file
      tls_key_file: /path/to/key/file
      tls_skip_verify: '1'
    vault_config_path: /etc/vault/vault.hcl
    vault_listener:
      address: 127.0.0.1:8200
      tls_disable: '1'
      tls_cert_file: /path/to/cert/file
      tls_key_file: /path/to/key/file
      tls_min_version: tls12
    vault_log_file: /var/log/vault.log
    vault_log_level: info
    vault_pid_file: /var/run/vault.pid
    vault_telemetry:
      disable_hostname: True
      statsd_address: 127.0.0.1:8125
      statsite_address: 127.0.0.1:8125

## Dependencies

 * https://galaxy.ansible.com/tkimball83/tkimball83/

## Example Playbook

    - hosts: servers
      roles:
        - role: tkimball83.vault
         vault_listener:
           address: "{{ ansible_default_ipv4.address }}:8200"
           tls_disable: '0'

## Partners

[![packagecloud](http://dka575ofm4ao0.cloudfront.net/pages-transactional_logos/retina/10543/gKme3F4XRaC5EyKJzKsA)](https://packagecloud.io)

Do you need trustworthy hosted package repositories?  Then packagecloud is for you.

A big thank you to packagecloud for supporting the open source community!
         
## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
