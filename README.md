Docker Focal Fossa
=========

![master](https://github.com/jake-morgan/ansible-role-docker-focal/workflows/master/badge.svg)
[![galaxy](https://img.shields.io/badge/galaxy-jake__morgan.docker__focal-5bbdbf.svg)](https://galaxy.ansible.com/jake_morgan/docker_focal)

Install Docker CE and Docker Compose on Ubuntu 20.04 LTS (Focal Fossa). Based heavily off of [geerlingguy.docker](https://github.com/geerlingguy/ansible-role-docker).

As 20.04, Ubuntu includes `docker.io` and `docker-compose` in the apt repositories the installation is much simpler than on previous Ubuntu versions.

Requirements
------------

Tested only on Ubuntu 20.04 LTS Focal Fossa. No guarantee it will work on other distros or Ubuntu versions.

Role Variables
--------------

| Variable | Description | Type| Required | Default |
|-|-|-|-|-|
| `uninstall_existing_docker` | Whether to uninstall existing docker packages | Bool | No | `false` |
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
    - role: jake-morgan.docker-focal
      vars:
        uninstall_existing_docker: true
        docker_install_compose: true
        docker_users:
          - my_user
          - ansible
```

License
-------

MIT
