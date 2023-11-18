# Base

Setup Ubuntu server.

## Role Variables

#### `base_dnsmasq_config`

- dnsmasq configuration file (see [man](https://linux.die.net/man/8/dnsmasq))
- type: multiline string
- required: true

#### `base_openresolv_config`

- openresolv configuration file (see
  [man](https://manpages.debian.org/bullseye/manpages/resolv.conf.5.en.html))
- type: multiline string
- required: true

#### `base_docker_config`

- docker configuration file (see
  [docs](https://docs.docker.com/engine/reference/commandline/dockerd/#daemon-configuration-file))
- type: map

#### `base_groups`

- groups to create, see group module
  [doc](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/group_module.html)
  for options
- type: list of maps

#### `base_users`

- users to create, see users module
  [doc](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/user_module.html)
  for options. Users previously created with this role and no longer present in
  `base_users` will be deleted automaticaly
- type: list of maps

#### `base_packages`

- list of apt packages to install
- type: list

#### `base_sysctl`

- `/proc/sys` values with sysctl
- type: list of maps

#### `base_limits`

- manage `limits.conf`
- type: list of maps

#### `base_directories`

- directories to create, see file module
  [doc](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html)
- type: list of maps

#### `base_files`

- files to create, see file module
  [doc](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/copy_module.html)
- type: list of maps

## Tags

#### `sysctl`

- configure sysctl entries

#### `limits`

- manage `/etc/security/limits.conf`

#### `users`

- manage users and groups

#### `directories`

- create directories

#### `files`

- create files

#### `packages`

- install packages

#### `dnsmasq`

- configure dnsmasq

#### `docker`

- configure docker

## Author

- **Anatolios Laskaris** - [nahsi](https://github.com/nahsi)
