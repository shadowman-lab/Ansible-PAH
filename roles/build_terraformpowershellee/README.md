<!-- This was created with Claude Code -->

build_terraformpowershellee
===========================

An Ansible role for build terraformpowershellee.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ee_version**: Variable used in: {{ pah_user }}
  - Default: `3`

* **version**: Configuration parameter for ansible.builtin.set_fact task
  - Default: `latest`

* **_github_api_headers**: Variable used in: Discover latest version of Powershell
  - Default: `{{ {'GITHUB_TOKEN': lookup('ansible.builtin.env', 'GITHUB_TOKEN')} if (lookup('ansible.builtin.env', 'GITHUB_TOKEN')) else {} }}`

* **dest_dir**: Variable used in: Create the directory if it does not exist
  - Default: `/home/ansible/ansible/builder/terraformpowershellee/`

* **pah_name**: Variable used in: {{ pah_user }}
  - Default: `aap.shadowman.dev`

* **image_name**: Variable used in: Delete old EE
  - Default: `terraformpowershellee`

* **bindep_file**: Binary path
  - Default: `bindep.txt`

* **galaxy_requirements_file**: Configuration parameter for build_terraformpowershellee
  - Default: `requirements.yml`

* **python_requirements_file**: Configuration parameter for build_terraformpowershellee
  - Default: `requirements.txt`

* **ee_base_image**: Image identifier or name
  - Default: `aap.shadowman.dev/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **ee_base_sig_name**: Resource name
  - Default: `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **galaxy_keyring**: Variable used in: Build new EE on version 1 without signature verification
  - Default: `/certs/fullkeyring.kbx`

* **ee_package_manager_path**: File system path
  - Default: `/usr/bin/microdnf`

* **ee_python_interpreter**: Configuration parameter for build_terraformpowershellee
  - Default: `{'python_path': '/usr/bin/python3.12'}`

* **ee_build_files**: Configuration parameter for build_terraformpowershellee
  - Default: `[{'src': '/home/ansible/ansible/builder/terraformpowershellee/ansible.cfg', 'dest': 'configs'}, {'src': '/certs/shadowman_cert.cer', 'dest': 'certs'}, {'src': '/certs/shadowman_private.key', 'dest': 'certs'}, {'src': '/certs/certificate.pfx', 'dest': 'certs'}, {'src': '/certs/service-ca-cert.crt', 'dest': 'certs'}]`

* **ee_bindep**: Binary path
  - Default: `['git [platform:rpm]', 'pkgconf-pkg-config [platform:rpm]', 'systemd-devel [platform:rpm]', 'gcc [platform:rpm]', 'python3.12-devel [platform:rpm]']`

* **ee_python**: Configuration parameter for build_terraformpowershellee
  - Default: `['jmespath']`

* **ee_collections**: Configuration parameter for build_terraformpowershellee
  - Default: `[{'name': 'ansible.controller'}, {'name': 'ansible.eda'}, {'name': 'ansible.hub'}, {'name': 'ansible.platform'}, {'name': 'cloud.terraform'}, {'name': 'community.general'}, {'name': 'community.vmware'}, {'name': 'hashicorp.terraform'}, {'name': 'infra.aap_configuration'}, {'name': 'vmware.vmware_rest'}]`

* **ee_prepend_galaxy**: Configuration parameter for build_terraformpowershellee
  - Default: `['ADD _build/configs/ansible.cfg /etc/ansible/ansible.cfg']`

* **ee_append_final**: Application name or identifier
  - Default: `['RUN microdnf install -y yum-utils', 'RUN dnf config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo', 'RUN dnf install -y terraform', 'RUN dnf install -y https://github.com/PowerShell/PowerShell/releases/download/v{{ version }}/powershell-{{ version }}-1.rh.x86_64.rpm', "RUN /opt/microsoft/powershell/7/pwsh -Command 'Install-Module VMware.PowerCLI -Scope AllUsers -Confirm:$False -Force'", "RUN /opt/microsoft/powershell/7/pwsh -Command 'Install-Module -Name VMware.Vim -RequiredVersion 8.3.0.24145081 -Scope AllUsers -Confirm:$False -Force'", "RUN /opt/microsoft/powershell/7/pwsh -Command 'Set-PowerCLIConfiguration -Scope AllUsers -ParticipateInCEIP $false -Confirm:$False'", "RUN /opt/microsoft/powershell/7/pwsh -Command 'Set-PowerCLIConfiguration -Scope AllUsers -InvalidCertificateAction Ignore -Confirm:$False'", 'COPY _build/certs/shadowman_cert.cer /certs/shadowman_cert.cer', 'COPY _build/certs/shadowman_private.key /certs/shadowman_private.key', 'COPY _build/certs/certificate.pfx /certs/certificate.pfx', 'COPY _build/certs/service-ca-cert.crt /certs/service-ca-cert.crt', 'RUN microdnf reinstall tzdata -y', 'RUN rm -f /etc/ansible/ansible.cfg', 'RUN microdnf clean all', 'RUN dnf clean all']`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: build_terraformpowershellee
      vars:
        ee_version: <value>
        version: <value>
        _github_api_headers: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
