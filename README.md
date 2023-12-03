# [Ansible role mount](#mount)

Configure mounts on your system

|GitHub|Downloads|Version|
|------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-mount/actions/workflows/molecule.yml/badge.svg)](https://github.com/mullholland/ansible-role-mount/actions/workflows/molecule.yml)|[![downloads](https://img.shields.io/ansible/role/d/mullholland/mount)](https://galaxy.ansible.com/mullholland/mount)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-mount.svg)](https://github.com/mullholland/ansible-role-mount/releases/)|
## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-mount/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  vars:
    mount_requests:
      - path: "/mnt/tmp"
        mode: "1777"
        src: "/tmp"
        fstype: "none"
        opts: "bind"

  roles:
    - role: "mullholland.mount"
```



## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-mount/blob/master/defaults/main.yml):

```yaml
---
# Mount dependencies like nfs-client-tools must be installed seperately
mount_requests: []
# mount_requests:
#   - path: "/mnt/backups"       # Required
#     owner: "root"              # Optional (Default 'root')
#     group: "root"              # Optional (Default 'root')
#     mode: "0750"               # Optional (Default '7500')
#     src: "10.0.0.10:/backups"  # Optional (Default 'omit')
#     boot: "true"               # Optional (Default 'omit')
#     fstype: "nfs"              # Optional (Required when state is present or mounted.)
#     opts: "defaults"           # Optional (Default 'omit')
#     dump: "0"                  # Optional (Default 'omit')
#     pass: "0"                  # Optional (Default 'omit')
#     state: "mounted"           # Optional (Default 'mounted')
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-mount/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/mullholland/ansible-role-mount/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/mullholland/enterpriselinux)|all|
|[Amazon](https://hub.docker.com/r/mullholland/amazonlinux)|Candidate|
|[Fedora](https://hub.docker.com/r/mullholland/fedora/)|all|
|[Ubuntu](https://hub.docker.com/r/mullholland/ubuntu)|all|
|[Debian](https://hub.docker.com/r/mullholland/debian)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-mount/issues).

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-mount/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)
