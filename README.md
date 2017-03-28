neovim-conf
============

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-neovim-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-neovim-conf)

Install your neovim configuration hosted on the GitHub.

https://galaxy.ansible.com/suzuki-shunsuke/neovim-conf/

Requirements
------------

* [motemen/ghq](https://github.com/motemen/ghq)

The directory structure of the repository where your vim config is hosted must be in the following manner.

```
(repository root)/
  init.vim
```

Role Variables
--------------

* neovim_conf_repo: The remote repository where your neovim config is hosted.
* ghq_executable: The executable path of ghq command. The default is "ghq".
* xdg_config_home: XDG_CONFIG_HOME. The default is the environment variable XDG_CONFIG_HOME or ~/.config
* neovim_conf_undodir: neovim undodir. If this variable is set, undodir is created

Dependencies
------------

* [suzuki-shunsuke.ghq-module](https://galaxy.ansible.com/suzuki-shunsuke/ghq-module/)

Example Playbook
----------------

```yaml
- hosts: servers
  vars:
    ghq_executable: /home/vagrant/.go/bin/ghq
  roles:
  - role: suzuki-shunsuke.neovim-conf
    neovim_conf_repo: suzuki-shunsuke/neovim.conf
```

License
-------

MIT
