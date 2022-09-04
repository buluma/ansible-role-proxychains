# [proxychains](#proxychains)

Install proxychains

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-proxychains/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-proxychains/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-proxychains/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-proxychains)|[![quality](https://img.shields.io/ansible/quality/60252)](https://galaxy.ansible.com/buluma/proxychains)|[![downloads](https://img.shields.io/ansible/role/d/60252)](https://galaxy.ansible.com/buluma/proxychains)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-proxychains.svg)](https://github.com/buluma/ansible-role-proxychains/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-proxychains.svg)](https://github.com/buluma/ansible-role-proxychains/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-proxychains.svg)](https://github.com/buluma/ansible-role-proxychains/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  tasks:
    - name: "Include buluma.proxychains"
      ansible.builtin.include_role:
        name: "buluma.proxychains"
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.python_pip
    - role: buluma.epel
    - role: buluma.pip
```



## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-proxychains/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|
|[buluma.python_pip](https://galaxy.ansible.com/buluma/python_pip)|[![Build Status GitHub](https://github.com/buluma/ansible-role-python_pip/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-python_pip/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-python_pip/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-python_pip)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Build Status GitHub](https://github.com/buluma/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-epel/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-epel/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-epel)|
|[buluma.pip](https://galaxy.ansible.com/buluma/pip)|[![Build Status GitHub](https://github.com/buluma/ansible-role-pip/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-pip/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-pip/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-pip)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-proxychains/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|ubuntu|all|
|debian|all|
|el|8|
|fedora|all|

The minimum version of Ansible required is 2.1, tests have been done to:

- The previous version.
- The current version.
- The development version.



If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-proxychains/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-proxychains/blob/master/CHANGELOG.md)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)
