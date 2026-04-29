<!-- This was created with Claude Code -->

build_networkee
===============

An Ansible role for build networkee.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ee_version**: Variable used in: {{ pah_user }}
  - Default: `3`

* **dest_dir**: Variable used in: Create the directory if it does not exist
  - Default: `/home/ansible/ansible/builder/networkee/`

* **pah_name**: Variable used in: {{ pah_user }}
  - Default: `aap.shadowman.dev`

* **image_name**: Variable used in: Delete old EE
  - Default: `networkee`

* **galaxy_requirements_file**: Configuration parameter for build_networkee
  - Default: `requirements.yml`

* **python_requirements_file**: Configuration parameter for build_networkee
  - Default: `requirements.txt`

* **ee_base_image**: Image identifier or name
  - Default: `aap.shadowman.dev/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **ee_base_sig_name**: Resource name
  - Default: `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **galaxy_keyring**: Variable used in: Build new EE on version 1 without signature verification
  - Default: `/certs/fullkeyring.kbx`

* **ee_package_manager_path**: File system path
  - Default: `/usr/bin/microdnf`

* **ee_python_interpreter**: Configuration parameter for build_networkee
  - Default: `{'python_path': '/usr/bin/python3.12'}`

* **ee_build_files**: Configuration parameter for build_networkee
  - Default: `[{'src': '/home/ansible/ansible/builder/networkee/ansible.cfg', 'dest': 'configs'}]`

* **ee_python**: Configuration parameter for build_networkee
  - Default: `['genie', 'pyats', 'pynautobot', 'scp']`

* **ee_collections**: Configuration parameter for build_networkee
  - Default: `[{'name': 'ansible.controller'}, {'name': 'ansible.netcommon'}, {'name': 'ansible.scm'}, {'name': 'ansible.utils'}, {'name': 'arista.eos'}, {'name': 'arubanetworks.aoscx'}, {'name': 'cisco.ios'}, {'name': 'community.general'}, {'name': 'f5networks.f5_modules'}, {'name': 'netbox.netbox'}, {'name': 'netscaler.adc'}, {'name': 'networktocode.nautobot'}, {'name': 'network.acls'}, {'name': 'network.backup'}, {'name': 'network.base'}, {'name': 'network.bgp'}, {'name': 'network.interfaces'}, {'name': 'network.ospf'}, {'name': 'network.telemetry'}, {'name': 'network.vpn'}, {'name': 'shadowman.reports'}, {'name': 'vyos.vyos'}]`

* **ee_prepend_galaxy**: Configuration parameter for build_networkee
  - Default: `['ADD _build/configs/ansible.cfg /etc/ansible/ansible.cfg']`

* **ee_append_final**: Application name or identifier
  - Default: `['RUN rm -f /etc/ansible/ansible.cfg', 'RUN microdnf clean all']`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: build_networkee
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
