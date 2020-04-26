Docker Focal Fossa
=========

![master](https://github.com/jake-morgan/ansible-role-docker-focal/workflows/master/badge.svg)

Install Docker CE and Docker Compose on Ubuntu 20.04 LTS (Focal Fossa). Based heavily off of [geerlingguy.docker](https://github.com/geerlingguy/ansible-role-docker).

As 20.04, Ubuntu includes `docker.io` and `docker-compose` in the apt repositories the installation is much simpler than on previous Ubuntu versions.

Requirements
------------

Tested only on Ubuntu 20.04 LTS Focal Fossa. No guarantee it will work on other distros or Ubuntu versions.

Role Variables
--------------

| Variable | Description | Type| Required | Default |
|-|-|-|-|-|
| `docker_install_compose` | Whether to install Docker Compose | Bool | No | `true` |
| `docker_users` | List of users to add to the `docker` group | List | No | `[]` |

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: jake-morgan.docker-focal-fossa
      vars:
        docker_install_compose: true
        docker_users:
          - my_user
          - ansible
```

License
-------

MIT
