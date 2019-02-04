# Ansible Role: Linux_kernel_module

An Ansible Role that allows to load kernel modules for Linux.

Each module is loaded from a file created `/etc/modprobe.d/`.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    kernel_modules: []                          # a liste of kernel modules
      - name: [mandatory]                       # the name of a module
        state: present                          # present|absent
        params: {}                              # optional parameters to load
    
The list of kernel modules to load.
Each item must include the `name` of the module and its optional `parameters`.

## Dependencies

None.

## Example Playbook

    - hosts: webservers
      roles:
        - role: t18s.fr_kernel_modules:
          - name: ip_tables
            state: present
            params: {}
        
          - name: ip6_tables
            state: present
            params: {}

## Todo

None.

## License

```
Copyright (c) 2018, 2019 Tristan Weil <titou@lab.t18s.fr>

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```
