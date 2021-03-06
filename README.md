# Ansible Collection - mafalb.ansible

|||
|---|---|
|master|![master branch](https://github.com/mafalb/ansible-collection-ansible/workflows/CI/badge.svg)|
|dev|![dev branch](https://github.com/mafalb/ansible-collection-ansible/workflows/CI/badge.svg?branch=dev)|

A collection for ansible related things.

We recommend to set [INTERPRETER_PYTHON](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#interpreter-python) to auto to avoid confusion between python 2 and 3.

For reference here is the link to the source code for INTERPRETER_PYTHON_DISTRO_MAP [lib/ansible/config/base.yml](https://raw.githubusercontent.com/ansible/ansible/devel/lib/ansible/config/base.yml)

## Roles

### [mafalb.ansible.molecule](roles/molecule/README.md)

### [mafalb.ansible.node](roles/node/README.md)

## Playbooks

There are two standalone playbooks that could help with develop ansible things. One playbook that creates a new collection from a template and one playbook that creates a new role.

### collection-init.yml

Initialize a new collection:

```sh
$ pwd
.../ansible_collections
$ ansible-playbook mafalb/ansible/playbooks/collection-init.yml -e collection=mafalb.squid
```

necessary variables

```collection```

```author```

optional variables

```skeleton_path```

### role-init.yml

Initialize a new role inside a collection

```sh
$ pwd
.../ansible_collections/mafalb/squid/roles
$ ansible-playbook playbooks/role-init.yml -e role=mafalb.squid.testrole
```

Initialize a new role outside a collection

```sh
$ pwd
.../anywhere/outside/a/collection
$ ansible-playbook playbooks/role-init.yml -e role=mafalb.testrole
```

### Mandatory variables:

```role``` can take two formats

```mafalb.collection_name.role_name``` for initializing inside a collection

```mafalb.role_name``` for initializing a classic standalone role

---

```author```

### Optional variables:

```skeleton_path: path to skeleton``` defaults to a skeleton shipped with this collection

```license: GPLv3``` specify the license, defaults to GPLv3

## License

GPLv3
