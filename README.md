# Ansible Chezmoi

Installs [chezmoi](https://www.chezmoi.io/) on Ubuntu and Debian servers.

## Requirements

If you set the `chezmoi_install_method` to `"snap"`, then the guest needs to have snap installed.

## Role Variables

All the variables are documented in the [`defaults/main.yml`](defaults/main.yml) file.

```yaml
chezmoi_install_method: "download"
```

Set this to `"snap"` to install chezmoi using snap. Other package managers are not supported as of right now. If you set this any other value, the role will download either the `deb` or the `rpm` file depending on the OS and install it.

```yaml
chezmoi_version: ""
```

Set this to the version you want to install. If left blank, it will detect the latest release from Github and download that. This setting is not used if `chezmoi_install_method` is set to `"snap"`.

**IMPORTANT**: The version MUST be a tag name on Github. For example, `"v2.1.2"` (note the 'v' in the beginning).

```yaml
chezmoi_init_url: ""
```

Set this to the URL of a repository with chezmoi's dotfiles you want to use. This option is passed as-is to chezmoi, which means you can use all kinds of options that chezmoi supports. For example, if your repo is on Github with the name `dotfiles`, then you can just set this variable to your Github username.

If you don't set this variable, then `chezmoi init` will be run without any options.

## Dependencies

Only Ansible's `community.general` collection is required to run this playbook.

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
