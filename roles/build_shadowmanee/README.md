<!-- This was created with Claude Code -->

build_shadowmanee
=================

An Ansible role for build shadowmanee.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ee_version**: Variable used in: {{ pah_user }}
  - Default: `3`

* **dest_dir**: Variable used in: Create the directory if it does not exist
  - Default: `/home/ansible/ansible/builder/shadowmanee/`

* **pah_name**: Variable used in: {{ pah_user }}
  - Default: `aap.shadowman.dev`

* **image_name**: Variable used in: Delete old EE
  - Default: `shadowmanee`

* **dev_image_name**: Variable used in: Build and push devee
  - Default: `devee`

* **bindep_file**: Binary path
  - Default: `bindep.txt`

* **python_requirements_file**: Configuration parameter for build_shadowmanee
  - Default: `requirements.txt`

* **galaxy_requirements_file**: Configuration parameter for build_shadowmanee
  - Default: `requirements.yml`

* **ee_base_image**: Image identifier or name
  - Default: `aap.shadowman.dev/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **ee_base_sig_name**: Resource name
  - Default: `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **repository**: Repository name or URL
  - Default: `shadowman`

* **galaxy_keyring**: ansible_config: ansible.cfg
  - Default: `/certs/fullkeyring.kbx`

* **ee_package_manager_path**: File system path
  - Default: `/usr/bin/microdnf`

* **ee_python_interpreter**: Configuration parameter for build_shadowmanee
  - Default: `{'python_path': '/usr/bin/python3.12'}`

* **ee_build_files**: Configuration parameter for build_shadowmanee
  - Default: `[{'src': '/home/ansible/ansible/builder/shadowmanee/ansible.cfg', 'dest': 'configs'}, {'src': '/certs/shadowman_cert.cer', 'dest': 'certs'}, {'src': '/certs/shadowman_private.key', 'dest': 'certs'}, {'src': '/certs/certificate.pfx', 'dest': 'certs'}, {'src': '/certs/service-ca-cert.crt', 'dest': 'certs'}]`

* **ee_bindep**: Binary path
  - Default: `['python3-jinja2 [platform:rpm]', 'which [platform:rpm]', 'git-core [platform:rpm]', 'libcurl-devel [platform:rpm]', 'systemd-devel [platform:rpm]', 'gcc [platform:rpm]', 'python3.12-devel [platform:rpm]', 'pkgconf-pkg-config [platform:rpm]', 'openssl-devel [platform:rpm]', 'libxml2-devel [platform:rpm]', 'libxslt-devel [platform:rpm]']`

* **ee_python**: Configuration parameter for build_shadowmanee
  - Default: `['python-jenkins']`

* **ee_collections**: Configuration parameter for build_shadowmanee
  - Default: `[{'name': 'amazon.aws'}, {'name': 'ansible.controller'}, {'name': 'ansible.eda'}, {'name': 'ansible.hub'}, {'name': 'ansible.posix'}, {'name': 'ansible.platform'}, {'name': 'ansible.utils'}, {'name': 'ansible.windows'}, {'name': 'azure.azcollection'}, {'name': 'cloud.terraform'}, {'name': 'community.postgresql'}, {'name': 'community.crypto'}, {'name': 'community.general'}, {'name': 'hashicorp.vault'}, {'name': 'community.vmware'}, {'name': 'community.windows'}, {'name': 'containers.podman'}, {'name': 'datadog.dd'}, {'name': 'dynatrace.oneagent'}, {'name': 'hashicorp.terraform'}, {'name': 'infra.aap_configuration'}, {'name': 'infra.windows_ops'}, {'name': 'microsoft.ad'}, {'name': 'microsoft.iis'}, {'name': 'redhat.insights'}, {'name': 'redhat.openshift'}, {'name': 'redhat.openshift_virtualization'}, {'name': 'redhat.satellite'}, {'name': 'servicenow.itsm'}, {'name': 'shadowman.reports'}, {'name': 'vmware.vmware_rest'}]`

* **ee_prepend_galaxy**: python_path: "/usr/bin/python3.10"
  - Default: `['ADD _build/configs/ansible.cfg /etc/ansible/ansible.cfg']`

* **ee_prepend_builder**: Configuration parameter for build_shadowmanee
  - Default: `['ENV PKGMGR_OPTS "--nodocs --setopt install_weak_deps=0 --enablerepo=rhocp-4.20-for-rhel-9-x86_64-rpms"']`

* **ee_prepend_final**: - ENV PKGMGR_OPTS "--nodocs --setopt install_weak_deps=0 --enablerepo=rhocp-4.17-for-rhel-8-x86_64-rpms --disablerepo=ubi-8-baseos-rpms --disablerepo=ubi-8-appstream-rpms --disablerepo=ubi-8-codeready-builder-rpms-8-x86_64"
  - Default: `['ENV PKGMGR_OPTS "--nodocs --setopt install_weak_deps=0 --enablerepo=rhocp-4.20-for-rhel-9-x86_64-rpms"']`

* **ee_append_final**: - ENV PKGMGR_OPTS "--nodocs --setopt install_weak_deps=0 --enablerepo=rhocp-4.17-for-rhel-8-x86_64-rpms --disablerepo=ubi-8-baseos-rpms --disablerepo=ubi-8-appstream-rpms --disablerepo=ubi-8-codeready-builder-rpms-8-x86_64"
  - Default: `['COPY _build/certs/shadowman_cert.cer /certs/shadowman_cert.cer', 'COPY _build/certs/shadowman_private.key /certs/shadowman_private.key', 'COPY _build/certs/certificate.pfx /certs/certificate.pfx', 'COPY _build/certs/service-ca-cert.crt /certs/service-ca-cert.crt', 'RUN microdnf reinstall tzdata -y', 'RUN rm -f /etc/ansible/ansible.cfg', 'RUN microdnf clean all']`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: build_shadowmanee
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
