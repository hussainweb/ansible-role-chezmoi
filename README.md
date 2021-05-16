# Ansible Chezmoi

Installs [chezmoi](https://www.chezmoi.io/) on Ubuntu and Debian servers.

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

## Dependencies

None

## Example Playbook

WIP.

```yaml
- hosts: servers
  roles:
    - { role: hussainweb.chezmoi, chezmoi_init_url: "github_username" }
```

## License

[MIT](LICENSE)

## Author Information

[Read more about me](https://github.com/hussainweb).
