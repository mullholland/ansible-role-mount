# [mount](#mount)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-mount/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-mount/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-mount/badges/master/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-mount)|[![quality](https://img.shields.io/ansible/quality/unset)](https://galaxy.ansible.com/mullholland/mount)|

description

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
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


## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
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





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [debian10](https://hub.docker.com/r/mullholland/docker-molecule-debian10)
-   [debian11](https://hub.docker.com/r/mullholland/docker-molecule-debian11)
-   [ubuntu1804](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu1804)
-   [ubuntu2004](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2004)
-   [ubuntu2204](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2204)
-   [centos7](https://hub.docker.com/r/mullholland/docker-molecule-centos7)
-   [centos-stream8](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream8)
-   [ubi8](https://hub.docker.com/r/mullholland/docker-molecule-ubi8)
-   [fedora34](https://hub.docker.com/r/mullholland/docker-molecule-fedora34)
-   [fedora35](https://hub.docker.com/r/mullholland/docker-molecule-fedora35)
-   [fedora36](https://hub.docker.com/r/mullholland/docker-molecule-fedora36)
-   [amazonlinux](https://hub.docker.com/r/mullholland/docker-molecule-amazonlinux)
-   [rockylinux8](https://hub.docker.com/r/mullholland/docker-molecule-rockylinux8)
-   [almalinux8](https://hub.docker.com/r/mullholland/docker-molecule-almalinux8)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The previous versions.
-   The current version.
-   The [devel](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-devel-from-github-with-pip) version.





If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-mount/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
