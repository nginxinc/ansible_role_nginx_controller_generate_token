NGINX Controller Generate Token
===============================

A role to generate and return an authentication token for NGINX Controller for use in other Roles or within a playbook.

Requirements
------------

[NGINX Controller](https://www.nginx.com/products/nginx-controller/)

Role Variables
--------------

-- All the below variables are required --

`nginx_controller_user_email` - The email address of the NGINX Controller user.

`nginx_controller_user_password` - The password that corresponds to the controller.user_email.

`nginx_controller_fqdn` - The DNS name of your NGINX Controller installation.

`nginx_controller_auth_token` - Variable returned by this Role and consumed by others to authenticate to the NGINX Controller API.

Dependencies
------------

none

Example Playbook
----------------

To use this role you can create a playbook such as the following:

```yaml
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

License
-------

[Apache License, Version 2.0](./LICENSE)

Author Information
------------------

[Brian Ehlert](https://github.com/brianehlert)

[Alessandro Fael Garcia](https://github.com/alessfg)

[Daniel Edgar](https://github.com/aknot242)

&copy; [NGINX, Inc.](https://www.nginx.com/) 2020
