# Ansible Role: Bibata Cursor

[![CI](https://github.com/pluggero/ansible-role-bibata-cursor/actions/workflows/ci.yml/badge.svg)](https://github.com/pluggero/ansible-role-bibata-cursor/actions/workflows/ci.yml) [![Ansible Galaxy downloads](https://img.shields.io/ansible/role/d/pluggero/bibata_cursor?label=Galaxy%20downloads&logo=ansible&color=%23096598)](https://galaxy.ansible.com/ui/standalone/roles/pluggero/bibata_cursor)

An Ansible Role that installs a selected bibata cursor type (https://github.com/ful1e5/Bibata_Cursor).

## Requirements

None.

## Role Variables

- **NOTE**: To make sure the cursor is displayed correctly in Qt applications, you have to set environment variables:
  - `XCURSOR_SIZE` to the size of the cursor
  - `XCURSOR_THEME` to the name of the cursor theme

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
bibata_cursor_version: "x.x.x"
```

The version of the installed bibata cursor (https://github.com/ful1e5/Bibata_Cursor) can be defined with `bibata_cursor_version`.

```yaml
bibata_cursor_type: "Ice"
```

The cursor to be installed can be defined with `bibata_cursor_type`.
Available options are:

- "Ice"
- "Classic"
- "Amber"

```yaml
bibata_cursor_size: "20"
```

The size of the cursor can be defined with `bibata_cursor_size`.
Available options are: 16, 20, 22, 24, 28, 32, 40, 48, 56, 64, 72, 80, 88, 96

```yaml
bibata_cursor_install_method: "dynamic"
```

The method used to install bibata cursor can be defined in the variable `bibata_cursor_install_method`.
The following methods are available:

- `source`: Installs bibata cursor from source
- `package`: Installs bibata cursor from the package manager of the distribution
  - **NOTE**: This method installs the latest version available in the package manager and not the version defined in `bibata_cursor_version`.
- `dynamic`: Installs bibata cursor from package manager if available in the correct version, otherwise installs from source

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - pluggero.bibata_cursor
```

## License

MIT / BSD

## Author Information

This role was created in 2025 by Robin Plugge.
