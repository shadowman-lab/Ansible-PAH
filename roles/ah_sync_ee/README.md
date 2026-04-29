<!-- This was created with Claude Code -->

ah_sync_ee
==========

An Ansible role for ah sync ee.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ee_image**: Variable used in: Sync Remote EE using Ansible Hub collection
  - Default: `ansible-automation-platform/ee-minimal-rhel9`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ah_sync_ee
      vars:
        ee_image: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
