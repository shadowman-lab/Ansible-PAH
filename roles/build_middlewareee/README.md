<!-- This was created with Claude Code -->

build_middlewareee
==================

An Ansible role for build middlewareee.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ee_version**: Variable used in: {{ pah_user }}
  - Default: `3`

* **dest_dir**: Variable used in: Create the directory if it does not exist
  - Default: `/home/ansible/ansible/builder/middlewareee/`

* **pah_name**: Variable used in: {{ pah_user }}
  - Default: `aap.shadowman.dev`

* **image_name**: Variable used in: Delete old EE
  - Default: `middlewareee`

* **galaxy_requirements_file**: Configuration parameter for build_middlewareee
  - Default: `requirements.yml`

* **ee_base_image**: Image identifier or name
  - Default: `aap.shadowman.dev/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **ee_base_sig_name**: Resource name
  - Default: `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **galaxy_keyring**: Variable used in: Build new EE on version 1 without signature verification
  - Default: `/certs/fullkeyring.kbx`

* **ee_package_manager_path**: File system path
  - Default: `/usr/bin/microdnf`

* **ee_python_interpreter**: Configuration parameter for build_middlewareee
  - Default: `{'python_path': '/usr/bin/python3.12'}`

* **ee_build_files**: Configuration parameter for build_middlewareee
  - Default: `[{'src': '/home/ansible/ansible/builder/middlewareee/ansible.cfg', 'dest': 'configs'}, {'src': '/certs/shadowman_cert.cer', 'dest': 'certs'}, {'src': '/certs/shadowman_private.key', 'dest': 'certs'}]`

* **ee_collections**: Configuration parameter for build_middlewareee
  - Default: `[{'name': 'ansible.posix'}, {'name': 'community.postgresql'}, {'name': 'redhat.eap'}, {'name': 'redhat.jbcs'}]`

* **ee_prepend_galaxy**: Configuration parameter for build_middlewareee
  - Default: `['ADD _build/configs/ansible.cfg /etc/ansible/ansible.cfg']`

* **ee_append_final**: Application name or identifier
  - Default: `['COPY _build/certs/shadowman_cert.cer /certs/shadowman_cert.cer', 'COPY _build/certs/shadowman_private.key /certs/shadowman_private.key', 'RUN rm -f /etc/ansible/ansible.cfg', 'RUN microdnf clean all']`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: build_middlewareee
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
