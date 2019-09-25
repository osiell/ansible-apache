# Apache 2 [![Build Status](https://travis-ci.org/osiell/ansible-apache.png)](https://travis-ci.org/osiell/ansible-apache)

Ansible role to install and configure Apache 2.

This role only install Apache packages using the standard Debian/Ubuntu APT
repositories, and configure some common parameters (listening ports, security
options...) without altering the file layouts supplied by the distribution.

Minimum Ansible Version: 1.8

## Systems supported

* Debian
    - Squeeze   (6)
    - Wheezy    (7)
    - Jessie    (8)
    - Stretch   (9)
    - Buster    (10)
* Ubuntu
    - Precise   (12.04)
    - Trusty    (14.04)

## Example (Playbook)

```yaml
- name: Web Server
  hosts: web_server
  roles:
    - apache
```

## Variables

```yaml
apache_package: apache2-mpm-worker

# Configuration
apache_config_disable_default_sites: False
#   - Ports
apache_config_namevirtualhost: ['*:80']
apache_config_http_ports: [80]
apache_config_https_ports: [443]
#   - Security
apache_config_server_tokens: OS     # Full | OS | Minimal | Minor | Major | Prod
apache_config_server_signature: On  # On | Off | EMail
apache_config_trace_enable: Off     # On | Off | extended
```
