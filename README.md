# Ansible Role: linux_kernel_module

An Ansible Role that allows to load kernel modules for Linux.

Each module is loaded from a file created `/etc/modprobe.d/`.

[![Actions Status](https://github.com/tristan-weil/ansible-role-linux_kernel_module/workflows/molecule/badge.svg?branch=master)](https://github.com/tristan-weil/ansible-role-linux_kernel_module/actions)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| linux_kernel_modules | []      | a list of <*kernel module*> |

### <*kernel module*>

A *kernel module* represents a kernel module.

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |
| name          | the name of the module to load |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| state         | present | *present / absent*: to load or unload a module
| params        | {}      | a dictionnary of optional parameters

## Example Playbook

    - hosts: 'webservers'
      roles:
        - role: 'ansible-role-linux_kernel_module:'
          linux_kernel_modules:
            - name: 'ip_tables'
              state: 'present'
              params: {}
        
            - name: 'ip6_tables'
              state: 'present'
              params: {}

## Todo

None.

## Dependencies

None.

## Supported platforms

See [meta/main.yml](https://github.com/tristan-weil/ansible-role-linux_kernel_module/blob/master/meta/main.yml)

## License

See [LICENSE.md](LICENSE.md)
