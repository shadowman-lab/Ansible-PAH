<!-- This was created with Claude Code -->

orphan_cleanup
==============

An Ansible role for orphan cleanup.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **pah_name**: Variable used in: Trigger PAH to clean orphaned content
  - Default: `aap.shadowman.dev`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: orphan_cleanup
      vars:
        pah_name: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
