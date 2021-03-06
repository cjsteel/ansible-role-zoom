zoom
=========

[![Build Status](https://travis-ci.org/csteel/ansible-role-zoom.svg?branch=master)](https://travis-ci.org/csteel/ansible-role-zoom)

The purpose of this role is to install and configure zoom on your system.

[Unit tests](https://travis-ci.org/csteel/ansible-role-zoom) are done on every commit and periodically.

If you find issues, please register them in [GitHub](https://github.com/csteel/ansible-role-zoom/issues)

## Testing

To test this role locally please use [Molecule](https://github.com/metacloud/molecule):

### quick start

#### set desired molecule environment variable(s)

For example to test again To change the current LTS version of ubuntu you would do this:

```shell
export namespace=robertdebock
export image=ubuntu
export tag=rolling # latest
```

#### Run your tests

```shell
molecule create
molecule converge
molecule test # creates, converges and deletes
```

### Molecule requirements

Install any Molecule requirements, for example:

```shell
pip install molecule ara
```

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/zoom.png "Dependency")

Requirements
------------

- A system installed with required packages to run Ansible. Hint: [bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap).
- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the last 3 release of Ansible.)

Role Variables
--------------

- zoom_parameter: Description of values. [default: value]

Dependencies
------------

- None known.

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.4|ansible 2.5|ansible 2.6|ansible 2.7|ansible devel|
|------------|-----------|-----------|-----------|-----------|-------------|
|alpine-edge*|yes|yes|yes|yes|yes*|
|alpine-latest|yes|yes|yes|yes|yes*|
|archlinux|yes|yes|yes|yes|yes*|
|centos-7|yes|yes|yes|yes|yes*|
|centos-latest|yes|yes|yes|yes|yes*|
|debian-latest|yes|yes|yes|yes|yes*|
|debian-stable|yes|yes|yes|yes|yes*|
|debian-unstable*|yes|yes|yes|yes|yes*|
|fedora-latest|yes|yes|yes|yes|yes*|
|fedora-rawhide*|yes|yes|yes|yes|yes*|
|opensuse-leap|yes|yes|yes|yes|yes*|
|ubuntu-artful|yes|yes|yes|yes|yes*|
|ubuntu-devel*|yes|yes|yes|yes|yes*|
|ubuntu-latest|yes|yes|yes|yes|yes*|

A single star means the build may fail, it's marked as an experimental build.

Example Playbook
----------------

```
---
- name: zoom
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: robertdebock.bootstrap
    - role: csteel.zoom
      zoom_parameter: value
```

To install this role:
- Install this role individually using `ansible-galaxy install csteel.zoom`

Sample roles/requirements.yml: (install with `ansible-galaxy install -r roles/requirements.yml
```
---
- name: robertdebock.bootstrap
- name: csteel.zoom
```

## License(s), prior art, inspiration and provenance

### ansible-role-skeleton

Apache License, Version 2.0, Copyright 2019 Robert de Bock (robert@meinit.nl)

### Previous incarnation of ansible-role-zoom

The MIT License (MIT) Copyright (c) 2015 Igor Mukhin <igor.mukhin@gmail.com>

### The creation of this version of ansible-role-zoom

A role skeleton generated using a customized version of the excellent
[ansible-role-skeleton](https://github.com/robertdebock/ansible-role-skeleton)
created by [Robert de Bock](https://robertdebock.nl/).

The generated skeleton was then blended with a clone this ansible role:
[github/author/ansible-role-zoom]((https://github.com/author/ansible-role-skeleton))

This was then merged with the generated Robert de Bock style skeleton and modified
in order to support additional Linux flavours, current Ansible development and
testing methods as well as other edits and additions to enhance functionality
and clairity.

Christopher Steel, March 21st, 2020