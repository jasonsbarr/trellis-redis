Note: this package isn't maintained anymore, but if you need to do something like upgrade the PHP version there are several forks available.

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
  src: marksabbath.trellis_redis
  version: 0.2.6
```

Run `ansible-galaxy install -r requirements.yml` to install the new role.<br>
Then, add the role into both server.yml **and** dev.yml:
```yaml
roles:
    ... other Trellis roles ...
    - { role: trellis-redis, tags: [redis]}
```

After adding the role to the above files and running the install, provision your Vagrant box with `vagrant reload --provision` (if it's running) or `vagrant provision` (if it's not). If you haven't provisioned the box yet simply run `vagrant up`.
