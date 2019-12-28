Role Name
=========

docker

[![Build Status](https://travis-ci.org/cmihai-ansible/docker.svg?branch=master)](https://travis-ci.org/cmihai-ansible/docker)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/crivetimihai/docker](https://galaxy.ansible.com/crivetimihai/docker)

```bash
ansible-galaxy install crivetimihai.docker
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```
docker_remove_packages: true
docker_enable_service: true
docker_copy_templates: true
docker_users:
  - user: devops
    group: docker
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install docker on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: docker is configured
      import_role:
        name: crivetimihai.docker
      vars:
        docker_remove_packages: true
        docker_enable_service: true
        docker_copy_templates: true
        docker_users:
          - user: devops
            group: docker
      tags: docker
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/crivetimihai/)
