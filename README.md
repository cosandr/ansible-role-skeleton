# ansible-role-skeleton

![GitHub](https://img.shields.io/github/license/cosandr/ansible-role-skeleton) ![GitHub last commit](https://img.shields.io/github/last-commit/cosandr/ansible-role-skeleton) ![GitHub issues](https://img.shields.io/github/issues-raw/cosandr/ansible-role-skeleton)

**[Molecule](https://molecule.readthedocs.io/en/latest/)-based role skeleton for use with ansible-galaxy to create a new ansible role.**

> This README does not explain how to use molecule. Please read the [docs](https://molecule.readthedocs.io/en/latest/) if you need to.

## Usage

```sh
git clone https://github.com/cosandr/ansible-role-skeleton.git
ansible-galaxy init --role-skeleton=ansible-role-skeleton ansible-role-<rolename>
cd ansible-role-<rolename>
# Delete .gitkeep and initialize origin remote to GitHub
sh init.sh
```

## Requirements

For all scenarios the following is required

- python3 (install via your os package manager)
- [Ansible 2.12 or higher](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

Then you can install the required python3 modules for all scenarios as an unprivileged user with the folliwing command:

```sh
pip3 install --user ansible-lint molecule molecule-vagrant molecule-podman yamllint
```

### Podman Scenario (default)

[Podman](https://podman.io) should work out of the box, after it is installed.

To install it, see the [official instructions](https://podman.io/getting-started/installation.html) or you can also use [ansible-role-podman](https://github.com/jam82/ansible-role-podman).

### Libvirt Scenario (kvm)

To use the predefined tests with kvm/libvirt you need to have the following packages installed:

- qemu
- virt-manager
- libvirt-dev package of your os
- [vagrant](http://vagrantup.com)

Your user needs to be in the `libvirt` or `libvirtd` system group depending on your distribution, because the qemu system domain is used.

After [installing vagrant](https://www.vagrantup.com/downloads.html) you need the [`vagrant-libvirt` plugin](https://github.com/vagrant-libvirt/vagrant-libvirt).

You can install it with:

```sh
vagrant plugin install vagrant-libvirt
```

## Author

[Andrei Costescu](https://github.com/cosandr/)

## Credits

Based on [jam82's skeleton](https://github.com/jam82/ansible-role-skeleton)
