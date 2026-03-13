# Ansible Role: chezmoi

[![Molecule CI](https://github.com/hussainweb/ansible-role-chezmoi/actions/workflows/ci.yml/badge.svg)](https://github.com/hussainweb/ansible-role-chezmoi/actions/workflows/ci.yml)

Ansible role to install [chezmoi](https://www.chezmoi.io/) and optionally initialize it with a source repository.

## Requirements

This role requires the `community.general` collection to be installed. You can install it with:

```bash
ansible-galaxy collection install community.general
```

## Supported Operating Systems

- Ubuntu 22.04 (Jammy)
- Ubuntu 24.04 (Noble)
- Debian 12 (Bookworm)
- Debian 13 (Trixie)
- Rocky Linux 9
- Rocky Linux 10

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

### `chezmoi_install_method`

Specify how to install chezmoi. If `"snap"`, then snapd is used (requires `snapd` to be present on the host). For all other values, the binary is downloaded directly from GitHub releases.

- **Default**: `"download"`

### `chezmoi_version`

The specific version of chezmoi to install. If left blank, it will automatically detect and install the latest release from GitHub. This setting is ignored if `chezmoi_install_method` is set to `"snap"`.

- **Default**: `""` (latest)

### `chezmoi_init_url`

A URL or GitHub username to use for `chezmoi init`. If provided, this will initialize chezmoi with the specified dotfiles repository.

- **Default**: `""`

## Example Playbook

### Basic installation

```yaml
- hosts: all
  roles:
    - role: hussainweb.chezmoi
```

### Install a specific version and initialize with dotfiles

```yaml
- hosts: all
  roles:
    - role: hussainweb.chezmoi
      vars:
        chezmoi_version: "v2.31.0"
        chezmoi_init_url: "hussainweb"
```

## License

MIT

## Author Information

This role was created by [Hussainweb](https://github.com/hussainweb).
