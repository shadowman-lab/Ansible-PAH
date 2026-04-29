<!-- This was created with Claude Code -->

build_shadowmandevspaces
========================

An Ansible role for build shadowmandevspaces.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ee_version**: Variable used in: {{ pah_user }}
  - Default: `3`

* **dest_dir**: Variable used in: Create the directory if it does not exist
  - Default: `/home/ansible/ansible/builder/shadowmaneedev/`

* **pah_name**: Variable used in: {{ pah_user }}
  - Default: `aap.shadowman.dev`

* **image_name**: Variable used in: Delete old EE
  - Default: `shadowmaneedev`

* **bindep_file**: Binary path
  - Default: `bindep.txt`

* **python_requirements_file**: Configuration parameter for build_shadowmandevspaces
  - Default: `requirements.txt`

* **galaxy_requirements_file**: Configuration parameter for build_shadowmandevspaces
  - Default: `requirements.yml`

* **ee_base_image**: Image identifier or name
  - Default: `aap.shadowman.dev/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **ee_base_sig_name**: Resource name
  - Default: `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel9:2.18`

* **galaxy_keyring**: Variable used in: Build new EE on version 1 without signature verification
  - Default: `/home/ansible/ansible/builder/shadowmanee/fullkeyring.kbx`

* **ee_package_manager_path**: File system path
  - Default: `/usr/bin/microdnf`

* **ee_python_interpreter**: Configuration parameter for build_shadowmandevspaces
  - Default: `{'python_path': '/usr/bin/python3.12'}`

* **ee_build_files**: Configuration parameter for build_shadowmandevspaces
  - Default: `[{'src': '/home/ansible/ansible/builder/shadowmaneedev/ansible.cfg', 'dest': 'configs'}, {'src': '/home/ansible/ansible/builder/shadowmaneedev/.bashrc', 'dest': 'configs'}, {'src': '/home/ansible/ansible/builder/shadowmaneedev/shells', 'dest': 'configs'}]`

* **ee_bindep**: Binary path
  - Default: `['python3-jinja2 [platform:rpm]', 'which [platform:rpm]', 'git [platform:rpm]', 'libcurl-devel [platform:rpm]', 'gcc [platform:rpm]', 'python3.12-devel [platform:rpm]', 'openssl-devel [platform:rpm]', 'libxml2-devel [platform:rpm]', 'libxslt-devel [platform:rpm]']`

* **ee_python**: Configuration parameter for build_shadowmandevspaces
  - Default: `['scp', 'pyats', 'genie', 'python-jenkins', 'pan-os-python==1.8.0', 'pan-python==0.17.0', 'panos-upgrade-assurance==0.3.0']`

* **ee_collections**: Configuration parameter for build_shadowmandevspaces
  - Default: `[{'name': 'amazon.aws'}, {'name': 'ansible.controller'}, {'name': 'ansible.eda'}, {'name': 'ansible.hub'}, {'name': 'ansible.netcommon'}, {'name': 'ansible.posix'}, {'name': 'ansible.platform'}, {'name': 'ansible.utils'}, {'name': 'ansible.windows'}, {'name': 'arista.eos'}, {'name': 'azure.azcollection'}, {'name': 'cisco.ios'}, {'name': 'cloud.terraform'}, {'name': 'community.postgresql'}, {'name': 'community.crypto'}, {'name': 'community.general'}, {'name': 'community.vmware'}, {'name': 'community.windows'}, {'name': 'containers.podman'}, {'name': 'datadog.dd'}, {'name': 'dynatrace.oneagent'}, {'name': 'f5networks.f5_modules'}, {'name': 'ibm.qradar'}, {'name': 'infra.aap_configuration'}, {'name': 'microsoft.ad'}, {'name': 'netscaler.adc'}, {'name': 'paloaltonetworks.panos'}, {'name': 'redhat.insights'}, {'name': 'redhat.openshift'}, {'name': 'redhat.rhv'}, {'name': 'redhat.satellite'}, {'name': 'servicenow.itsm'}, {'name': 'shadowman.reports'}, {'name': 'vmware.vmware_rest'}, {'name': 'vyos.vyos'}]`

* **ee_prepend_galaxy**: Configuration parameter for build_shadowmandevspaces
  - Default: `['ADD _build/configs/ansible.cfg /etc/ansible/ansible.cfg']`

* **ee_prepend_builder**: Configuration parameter for build_shadowmandevspaces
  - Default: `['ENV PKGMGR_OPTS "--nodocs --setopt install_weak_deps=0 --enablerepo=rhocp-4.17-for-rhel-8-x86_64-rpms"']`

* **ee_prepend_final**: Configuration parameter for build_shadowmandevspaces
  - Default: `['ENV PKGMGR_OPTS "--nodocs --setopt install_weak_deps=0 --enablerepo=rhocp-4.17-for-rhel-8-x86_64-rpms"']`

* **ee_append_final**: Application name or identifier
  - Default: `['RUN microdnf install -y yum-utils', 'RUN dnf config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo', 'RUN dnf install -y terraform', 'RUN microdnf reinstall tzdata -y', 'RUN git clone -b citrix.adc --single-branch https://github.com/netscaler/ansible-collection-netscaleradc.git /tmp/citrix', 'RUN pip3 install /tmp/citrix/deps/nitro-python-1.0_kamet.tar.gz', 'RUN rm -rf /tmp/citrix/', 'RUN rm -f /etc/ansible/ansible.cfg', 'RUN /usr/bin/microdnf install python3.11 python3.11-pip -y', 'RUN /usr/bin/python3.11 -m pip install --no-cache-dir ansible-dev-tools', 'RUN microdnf clean all', 'RUN dnf clean all', 'COPY _build/configs/shells /etc/shells', 'COPY _build/configs/.bashrc /home/runner/.bashrc', 'RUN printf "export CONTAINER_NAME=ansibleee\\n" >> /home/runner/.bashrc', 'RUN chgrp -R 0 /home && chmod -R g=u /etc/passwd /etc/group /home']`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: build_shadowmandevspaces
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
