# Ansible role [proxychains](https://galaxy.ansible.com/ui/standalone/roles/buluma/proxychains/documentation)

Install Proxychains forcing TCP connection to follow through proxy like TOR or any other SOCKS4, SOCKS5 or HTTP(S) proxy.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-proxychains/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-proxychains/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-proxychains.svg)](https://github.com/buluma/ansible-role-proxychains/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-proxychains.svg)](https://github.com/buluma/ansible-role-proxychains/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-proxychains.svg)](https://github.com/buluma/ansible-role-proxychains/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/proxychains)](https://galaxy.ansible.com/ui/standalone/roles/buluma/proxychains/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-proxychains/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  vars:
    dynamic_chain: true
    chain_len: 2
    tcp_read_time_out: 16000
    tcp_connect_time_out: 10000
  tasks:
    - name: "Include buluma.proxychains"
      ansible.builtin.include_role:
        name: "buluma.proxychains"
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-proxychains/blob/master/molecule/default/prepare.yml):

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

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-proxychains/blob/master/defaults/main.yml):

```yaml
---
# The option below identifies how the ProxyList is treated.
# only one option should be uncommented at time,
# otherwise the last appearing option will be accepted
#

# Dynamic - Each connection will be done via chained proxies
# all proxies chained in the order as they appear in the list
# at least one proxy must be online to play in chain
# (dead proxies are skipped)
dynamic_chain: false

# Strict - Each connection will be done via chained proxies
# all proxies chained in the order as they appear in the list
# all proxies must be online to play in chain
strict_chain: false

# Round Robin - Each connection will be done via chained proxies
# of chain_len length
# all proxies chained in the order as they appear in the list
# at least one proxy must be online to play in chain
# (dead proxies are skipped).
# the start of the current proxy chain is the proxy after the last
# proxy in the previously invoked proxy chain.
# if the end of the proxy chain is reached while looking for proxies
# start at the beginning again.
# These semantics are not guaranteed in a multithreaded environment.
round_robin_chain: false

# Random - Each connection will be done via random proxy
# (or proxy chain, see  chain_len) from the list.
# this option is good to test your IDS :)
random_chain: false

# Make sense only if random_chain or round_robin_chain
# chain_len = 2

# Quiet mode (no output from library)
# quiet_mode

# Set timeouts in milliseconds
tcp_read_time_out: 15000
tcp_connect_time_out: 8000
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-proxychains/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.python_pip](https://galaxy.ansible.com/buluma/python_pip)|[![Ansible Molecule](https://github.com/buluma/ansible-role-python_pip/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-python_pip/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-python_pip.svg)](https://github.com/shadowwalker/ansible-role-python_pip)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-epel.svg)](https://github.com/shadowwalker/ansible-role-epel)|
|[buluma.pip](https://galaxy.ansible.com/buluma/pip)|[![Ansible Molecule](https://github.com/buluma/ansible-role-pip/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-pip/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-pip.svg)](https://github.com/shadowwalker/ansible-role-pip)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-proxychains/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|all|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|8|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|

The minimum version of Ansible required is 2.1, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-proxychains/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-proxychains/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-proxychains/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)

