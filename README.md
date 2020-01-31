NGINC Controller generate token
=========

A role to generate an and return an authentication toekn for NGINX Contoller for use in other Roles or within a playbook.

Requirements
------------

NGINX Controller [](https://www.nginx.com/products/nginx-controller/)

Role Variables
--------------

user_email - the email adddress of the NGINX Controller user
user_password - the password that corresponds to the user_email
controller_fqdn - provide the DNS name of your NGINX Controller
controller_auth_token - variable returned by this Role and conmsed for others to authenticate to the NGINX Controller API

Dependencies
------------

none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers

      vars:
        controller_fqdn: controller.mydomain.com
        user_email: user@examlple.com
        user_password: mySecurePassword

      roles:
         - nginxinc.nginx-controller-generate-token
         - nginxinc.nginx-controller-agent

License
-------

Apache

Author Information
------------------

brianehlert
