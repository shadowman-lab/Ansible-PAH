<!-- This was created with Claude Code -->

# PAH Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-PAH)


This directory contains Ansible automation for pah management and operations.

## Overview

The PAH automation provides playbooks and roles for managing and configuring
pah infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [ah_login](roles/ah_login/README.md) | Role for ah login |
| [ah_sync_ee](roles/ah_sync_ee/README.md) | Role for ah sync ee |
| [ah_sync_repos](roles/ah_sync_repos/README.md) | Role for ah sync repos |
| [ah_update_controller](roles/ah_update_controller/README.md) | Role for ah update controller |
| [build_aristaee](roles/build_aristaee/README.md) | Role for build aristaee |
| [build_certee](roles/build_certee/README.md) | Role for build certee |
| [build_creationee](roles/build_creationee/README.md) | Role for build creationee |
| [build_middlewareee](roles/build_middlewareee/README.md) | Role for build middlewareee |
| [build_networkee](roles/build_networkee/README.md) | Role for build networkee |
| [build_nmapee](roles/build_nmapee/README.md) | Role for build nmapee |
| [build_securityee](roles/build_securityee/README.md) | Role for build securityee |
| [build_shadowmande](roles/build_shadowmande/README.md) | Role for build shadowmande |
| [build_shadowmandevspaces](roles/build_shadowmandevspaces/README.md) | Role for build shadowmandevspaces |
| [build_shadowmanee](roles/build_shadowmanee/README.md) | Role for build shadowmanee |
| [build_terraformpowershellee](roles/build_terraformpowershellee/README.md) | Role for build terraformpowershellee |
| [orphan_cleanup](roles/orphan_cleanup/README.md) | Role for orphan cleanup |
| [sync_de](roles/sync_de/README.md) | Role for sync de |
| [sync_ee](roles/sync_ee/README.md) | Role for sync ee |
| [sync_repos](roles/sync_repos/README.md) | Role for sync repos |
| [update_collection_remote](roles/update_collection_remote/README.md) | Role for update collection remote |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| arista_ee_build.yml | Playbook for arista ee build | localhost, ansibledev.shadowman.dev |
| cert_ee_build.yml | Playbook for cert ee build | localhost, ansibledev.shadowman.dev |
| creation_ee_build.yml | Playbook for creation ee build | localhost, ansibledev.shadowman.dev |
| middleware_ee_build.yml | Playbook for middleware ee build | localhost, ansibledev.shadowman.dev |
| network_ee_build.yml | Playbook for network ee build | localhost, ansibledev.shadowman.dev |
| nmap_ee_build.yml | Playbook for nmap ee build | ansibledev.shadowman.dev |
| orphan_cleanup.yml | Playbook for orphan cleanup | localhost |
| security_ee_build.yml | Playbook for security ee build | localhost, ansibledev.shadowman.dev |
| shadowman_de_build.yml | Playbook for shadowman de build | localhost, ansibledev.shadowman.dev |
| shadowman_ee_build.yml | Playbook for shadowman ee build | localhost, ansibledev.shadowman.dev |
| shadowman_ee_utils_build.yml | Playbook for shadowman ee utils build | localhost, ansibledev.shadowman.dev |
| shadowman_ee_utils_simple.yml | Playbook for shadowman ee utils simple | localhost, ansibledev.shadowman.dev |
| skopeo.yml | Playbook for skopeo | ansibledev.shadowman.dev |
| terraformpowershell_ee_build.yml | Playbook for terraformpowershell ee build | localhost, ansibledev.shadowman.dev |
| update_collection_remote_lists.yml | Playbook for update collection remote lists | localhost |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run middleware_ee_build.yml

# Run in stdout mode
ansible-navigator run middleware_ee_build.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - ah_sync_ee
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-PAH/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
