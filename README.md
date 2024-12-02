# README

# Ansible Role: ludus_windows_keyboard_layout ([Ludus](https://ludus.cloud))

An Ansible Role that installs specific keyboard layout to windows hosts. By default, will install french layout but can be modified using the var `ludus_windows_keyboard_layout`.


## Requirements

Working only for Windows hosts.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    # Layout that will be added to the windows Host (default to fr-FR)
    ludus_windows_keyboard_layout: fr-FR

## Dependencies

None.

## Example Playbook

```yaml
- hosts: ludus_windows_keyboard_layout_hosts
  roles:
    - rebrec.ludus_windows_keyboard_layout
  vars:
    - ludus_windows_keyboard_layout: fr-FR
```

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "{{ range_id }}-ad-dc-win2022-server-x64-1"
    hostname: "{{ range_id }}-DC01-2022"
    template: win2022-server-x64-template
    vlan: 10
    ip_last_octet: 11
    ram_gb: 6
    cpus: 4
    windows:
      sysprep: true
    domain:
      fqdn: ludus.domain
      role: primary-dc
    roles:
      - rebrec.ludus_windows_keyboard_layout

```

## License

GPLv3

## Author Information

This role was created by [rebrec](https://github.com/rebrec), for [Ludus](https://ludus.cloud/).
