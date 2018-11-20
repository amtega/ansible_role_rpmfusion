# Ansible EPEL repository role

This is an [Ansible](http://www.ansible.com) role which manages RPMFUSION repository.

## Requirements

[Ansible 2.7+](http://docs.ansible.com/ansible/latest/intro_installation.html)

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

## Dependencies

- [amtega.check_platform](https://galaxy.ansible.com/amtega/check_platform)
- [amtega.epel](https://galaxy.ansible.com/amtega/epel) if host has a centos/rhel 6 operating system.
- [amtega.proxy_client](https://galaxy.ansible.com/amtega/proxy_client). If you need a proxy for internet access fill this role variables.

## Example Playbook

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - amtega.rpmfusion

  vars:
    rpmfusion_state: present

    rpmfusion_validate_certs: false

    rpmfusion_free_enabled: 1
    rpmfusion_free_debuginfo_enabled: 1
    rpmfusion_free_source_enabled: 0

    rpmfusion_free_updates_enabled: 1
    rpmfusion_free_updates_debuginfo_enabled: 1
    rpmfusion_free_updates_source_enabled: 0

    rpmfusion_free_updates_testing_enabled: 0
    rpmfusion_free_updates_testing_debuginfo_enabled: 0
    rpmfusion_free_updates_testing_source_enabled: 0

    rpmfusion_nonfree_enabled: 1
    rpmfusion_nonfree_debuginfo_enabled: 1
    rpmfusion_nonfree_source_enabled: 0

    rpmfusion_nonfree_updates_enabled: 1
    rpmfusion_nonfree_updates_debuginfo_enabled: 0
    rpmfusion_nonfree_updates_source_enabled: 0

    rpmfusion_nonfree_updates_testing_enabled: 1
    rpmfusion_nonfree_updates_testing_debuginfo_enabled: 0
    rpmfusion_nonfree_updates_testing_source_enabled: 0
```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.rpmfusion/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2018 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Juan Antonio Valiño García.
