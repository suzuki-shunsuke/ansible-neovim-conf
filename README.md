# ansible-neovim-conf

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-neovim-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-neovim-conf)

ansible role to install neovim configurations

https://galaxy.ansible.com/suzuki-shunsuke/neovim-conf/

## Requirements

* git

The directory structure of the repository where your vim config is hosted must be in the following manner.

```
(repository root)/
  init.vim
```

## Role Variables

name | required | default | description
--- | --- | --- | ---
neovim_conf_repo | yes | |
neovim_conf_cloned_dest | yes | |
neovim_conf_undodir | no | | neovim's undodir path. If this variable is set, this directory is created
neovim_conf_xdg_config_home | no | `XDG_CONFIG_HOME` >> `{{ansible_env.HOME}}/.config` | XDG_CONFIG_HOME
neovim_conf_version | no | HEAD |

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: suzuki-shunsuke.neovim-conf
      neovim_conf_repo: https://github.com/suzuki-shunsuke/neovim.conf
      neovim_conf_cloned_dest: "{{ansible_env.HOME}}/repos/src/github.com/suzuki-shunsuke/neovim.conf"
      neovim_conf_undodir: "{{ansible_env.HOME}}/.neovimundo"
      neovim_conf_version: develop
```

## License

[MIT](LICENSE)
