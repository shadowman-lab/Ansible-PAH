<!-- This was created with Claude Code -->

build_creationee
================

An Ansible role for build creationee.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ee_version**: Variable used in: {{ pah_user }}
  - Default: `3`

* **dest_dir**: Variable used in: Create the directory if it does not exist
  - Default: `/home/ansible/ansible/builder/creation/`

* **pah_name**: Variable used in: {{ pah_user }}
  - Default: `aap.shadowman.dev`

* **image_name**: Variable used in: Delete old EE
  - Default: `shadowmancreationee`

* **bindep_file**: Binary path
  - Default: `bindep.txt`

* **galaxy_requirements_file**: Configuration parameter for build_creationee
  - Default: `requirements.yml`

* **ee_base_image**: Image identifier or name
  - Default: `aap.shadowman.dev/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **ee_base_sig_name**: Resource name
  - Default: `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **galaxy_keyring**: Variable used in: Build new EE on version 1 without signature verification
  - Default: `/certs/fullkeyring.kbx`

* **ee_package_manager_path**: File system path
  - Default: `/usr/bin/microdnf`

* **ee_python_interpreter**: Configuration parameter for build_creationee
  - Default: `{'python_path': '/usr/bin/python3.12'}`

* **ee_build_files**: Configuration parameter for build_creationee
  - Default: `[{'src': '/home/ansible/ansible/builder/creation/ansible.cfg', 'dest': 'configs'}]`

* **ee_bindep**: Binary path
  - Default: `['pkgconf-pkg-config [platform:rpm]', 'systemd-devel [platform:rpm]', 'gcc [platform:rpm]', 'python3.12-devel [platform:rpm]']`

* **ee_collections**: Configuration parameter for build_creationee
  - Default: `[{'name': 'ansible.controller'}, {'name': 'ansible.eda'}, {'name': 'ansible.hub'}, {'name': 'ansible.platform'}, {'name': 'containers.podman'}, {'name': 'infra.aap_configuration'}, {'name': 'infra.ee_utilities'}]`

* **ee_prepend_galaxy**: Configuration parameter for build_creationee
  - Default: `['ADD _build/configs/ansible.cfg /etc/ansible/ansible.cfg']`

* **ee_append_final**: Application name or identifier
  - Default: `['RUN rm -f /etc/ansible/ansible.cfg']`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: build_creationee
      vars:
        ee_version: <value>
        dest_dir: <value>
        pah_name: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
