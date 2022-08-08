# Ansible NGINX Controller Generate Token Role

# This repository has been archived. There will likely be no further development on the project and security vulnerabilities may be unaddressed.

A role to generate and return an authentication token for NGINX Controller for use in other Roles or within a playbook.

## Requirements

### NGINX Controller

A running [NGINX Controller](https://www.nginx.com/products/nginx-controller/) instance.

### Ansible

* This role is developed and tested with [maintained](https://docs.ansible.com/ansible/devel/reference_appendices/release_and_maintenance.html) versions of Ansible core (above `2.11`).
* You will need to run this role as a root user using Ansible's `become` parameter. Make sure you have set up the appropriate permissions on your target hosts.
* Instructions on how to install Ansible can be found in the [Ansible website](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#upgrading-ansible-from-version-2-9-and-older-to-version-2-10-or-later).

### Molecule (Optional)

* Molecule is used to test the various functionalities of the role. The recommended version of Molecule to test this role is `3.3`.
* Instructions on how to install Molecule can be found in the [Molecule website](https://molecule.readthedocs.io/en/latest/installation.html). _You will also need to install the Molecule Docker driver._

## Installation

### Ansible Galaxy

Use `ansible-galaxy install nginxinc.nginx_controller_generate_token` to install the latest stable release of the role on your system. Alternatively, if you have already installed the role, use `ansible-galaxy install -f nginxinc.nginx_controller_generate_token` to update the role to the latest release.

### Git

Use `git clone https://github.com/nginxinc/ansible_role_nginx_controller_generate_token.git` to pull the latest edge commit of the role from GitHub.

## Platforms

The NGINX Controller generate token Ansible role supports all platforms that support Ansible `2.11`, some of them being:

```yaml
Alpine:
  - all
Amazon Linux:
  - all
Amazon Linux 2:
  - all
CentOS:
  - all
Debian:
  - all
FreeBSD:
  - all
RHEL:
  - all
Ubuntu:
  - all
```

## Role Variables

| Variable | Default | Description | Required |
| -------- | ------- | ----------- | -------- |
| `nginx_controller_user_email` | `""` | The email address of the NGINX Controller user | Yes |
| `nginx_controller_user_password` | `""` | The password of the NGINX Controller user | Yes |
| `nginx_controller_fqdn` | `""` | The FQDN of NGINX Controller | Yes |
| `nginx_controller_validate_certs` | `false` | Whether NGINX Controller SSL cert should be validated or not | No |

In addition, this role returns the following variable:
`nginx_controller_auth_token` - Authentication token used to authenticate to the NGINX Controller API.

## Example Playbook

To use this role you can create a playbook such as the following:

```yaml
---
- hosts: localhost
  gather_facts: no
  tasks:
    - name: Retrieve the NGINX Controller auth token
      include_role:
        name: nginxinc.nginx_controller_generate_token
      vars:
        nginx_controller_user_email: "user@example.com"
        nginx_controller_user_password: "mySecurePassword"
        nginx_controller_fqdn: "controller.mydomain.com"
        nginx_controller_validate_certs: false
```

## Other NGINX Ansible Collections and Roles

You can find the Ansible NGINX Core collection of roles to install and configure NGINX Open Source, NGINX Plus, and NGINX App Protect [here](https://github.com/nginxinc/ansible-collection-nginx).

You can find the Ansible NGINX role to install NGINX OSS and NGINX Plus [here](https://github.com/nginxinc/ansible-role-nginx).

You can find the Ansible NGINX configuration role to configure NGINX [here](https://github.com/nginxinc/ansible-role-nginx-config).

You can find the Ansible NGINX App Protect role to install and configure NGINX App Protect WAF and NGINX App Protect DoS [here](https://github.com/nginxinc/ansible-role-nginx-app-protect).

You can find the Ansible NGINX Controller collection of roles to install and configure NGINX Controller [here](https://github.com/nginxinc/ansible-collection-nginx_controller).

You can find the Ansible NGINX Unit role to install NGINX Unit [here](https://github.com/nginxinc/ansible-role-nginx-unit).

## License

[Apache License, Version 2.0](https://github.com/nginxinc/ansible-role-nginx-config/blob/main/LICENSE)

## Author Information

[Alessandro Fael Garcia](https://github.com/alessfg)

[Brian Ehlert](https://github.com/brianehlert)

[Daniel Edgar](https://github.com/aknot242)

&copy; [F5 Networks, Inc.](https://www.f5.com/) 2020 - 2021
