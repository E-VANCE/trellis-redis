Trellis Redis 
=========

Ansible role to add Redis to Trellis server provisioning

This role is made to be used with [Trellis](https://github.com/roots/trellis).
It installs and configures Redis and the PECL php-redis extension on your server.

Get Started
----------------
Add the role to the requirements.yml file of Trellis :
```yaml
- name: trellis-redis
  src: jasonsbarr.trellis-redis
  version: 0.1.0
```

Run `ansible-galaxy install -r requirements.yml` to install the new role.<br>
Then, add the role into server.yml :
```yaml
roles:
    ... other Trellis roles ...
    - { role: trellis-redis, tags: [redis]}
```