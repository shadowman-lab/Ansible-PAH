<!-- This was created with Claude Code -->

sync_de
=======

An Ansible role for sync de.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **pah_name**: Variable used in: Sync Remote EE
  - Default: `aap.shadowman.dev`

* **ee_base_image**: Variable used in: Sync Remote EE using AH Configuration collection
  - Default: `ansible-automation-platform-26/de-minimal-rhel9`

* **builder_image**: Image identifier or name
  - Default: `ansible-automation-platform-24/ansible-builder-rhel8`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: sync_de
      vars:
        pah_name: <value>
        ee_base_image: <value>
        builder_image: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
