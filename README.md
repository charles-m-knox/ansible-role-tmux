# tmux

Ansible role that installs and configures `tmux`, the way I want.

## Requirements

There are no requirements for this, it should work out of the box with Ansible.

## Role Variables

Please see `defaults/main.yml` for variables that can all be set on a per-host
basis.

## Dependencies

None at the moment.

## Usage

First, create a `requirements.yml` in your Ansible setup if you haven't already,
here's an example:

```yaml
---
collections:
  - name: community.general
  - name: ansible.posix
  - name: community.crypto

roles:
  - name: charles-m-knox.tmux
    src: https://github.com/charles-m-knox/ansible-role-tmux.git
    scm: git
    version: main
```

Next, install it:

```bash
# include the -f flag to forceably re-install and get the latest (equivalent to
# upgrading)
ansible-galaxy role install -f -r requirements.yml
```

Now, in your `site.yml` (or whatever your playbook is named), use the role -
note that root access is required for some of the steps:

```yaml
- name: tmux
  hosts: all
  roles:
    - charles-m-knox.tmux
```

```bash
ansible-playbook site.yml --tags tmux --step
```

## License

MIT

## Author Information

<https://charlesmknox.com>
