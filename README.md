Ansible Role: Dotfiles
======================

Install dotfiles @ https://github.com/Djuuu/dotfiles

Role Variables
--------------

Available role variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
dotfiles_repo: "{{ dotfiles_clone_use_ssh | ternary(dotfiles_repo_ssh, dotfiles_repo_https) }}"

dotfiles_repo_https:    https://github.com/Djuuu/dotfiles.git
dotfiles_repo_ssh:          git@github.com:Djuuu/dotfiles.git

dotfiles_clone_use_ssh: false

dotfiles_repo_version: master

dotfiles_repo_local_destination: ~/.dotfiles

dotfiles_force_reset: false

dotfiles_backup: false

dotfiles_install_command:  "{{ dotfiles_repo_local_destination }}/install"

dotfiles_gitconfig: []
  #- { option: 'name',  value: me }
  #- { option: 'email', value: me@example.net }
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - djuuu.dotfiles
```

License
-------

Beerware License
