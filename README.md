Ansible role for local-tap
==================================

Installs Brew packages from local tap

[![GitHub Actions](https://github.com/mongodb-ansible-roles/ansible-role-local-tap/workflows/Molecule%20Test/badge.svg)](https://github.com/mongodb-ansible-roles/ansible-role-local-tap/actions?query=workflow%3A%22Molecule+Test%22)
[![GitHub Actions](https://github.com/mongodb-ansible-roles/ansible-role-local-tap/workflows/Release/badge.svg)](https://github.com/mongodb-ansible-roles/ansible-role-local-tap/actions?query=workflow%3A%22Release%22)

Requirements
------------

Homebrew must be installed in order to run this role. You may have to run `brew link --overwrite {package}@{version}` in order for the binary to be linked properly. You can always call the binaries directly at `/usr/local/Cellar`

Role Variables
--------------

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-------:|:--------:|
| `homebrew_tap_user` | The directory to install local taps in | string | `build` | `false` |
| `homebrew_tap_packages` | Brew packages with versions to install | object | `[]` | `true` |

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ansible-role-local-tap
      vars:
        homebrew_tap_packages:
          - name: doxygen
            version: 1.8.13
```

License
-------

[Apache License](LICENSE)
