Trellis Redis
=========

Ansible role to add Redis to Trellis server provisioning

This role is made to be used with [Trellis](https://github.com/roots/trellis).
It installs and configures Redis and the PECL php-redis extension on your server.

Get Started
----------------
Add the role to the `galaxy.yml` file of Trellis :
```yaml
- name: trellis-redis
  src: https://github.com/E-VANCE/trellis-redis
  type: git
  version: 0.3.1
```

Run `ansible-galaxy install -r galaxy.yml` (or `trellis galaxy install` if you have [trellis-cli](https://github.com/roots/trellis-cli)) to install the new role.<br>
Then, add the role into both `server.yml` **and** `dev.yml`:
```yaml
roles:
    ... other Trellis roles ...
    - { role: trellis-redis, tags: [redis]}
```

After adding the role to the above files and running the install, provision your Vagrant box with `vagrant reload --provision` (if it's running) or `vagrant provision` (if it's not). If you haven't provisioned the box yet simply run `vagrant up` or `trellis up` if you have [trellis-cli](https://github.com/roots/trellis-cli) installed.

Custom config
----------------
You may want to edit the `maxmemory`-values in `/defaults/main.yml` if for example 2 GB isn't enough for your setup or another policy should be used.

A future version of this role will include the possibility for customisations to be made without the fear of overwrites on updating – thus be aware that **any modifications made here are *not* Update-proof**!
