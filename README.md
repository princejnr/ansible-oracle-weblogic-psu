# psu-apply

Ansible role to apply Oracle patches (PSU) to WebLogic servers.


## Role Variables

### vars/main.yml

* psu:  dictionary variable with latest PSU information for 10.3.4 and 10.3.6

* opatch: dictionary variable with latest opatch version for 10.3.4 and 10.3.6

* oneoff_patches: dictionary variable with list of one-off patches to apply for 10.3.4 and 10.3.6

### defaults/main.yml

* patch_name: July2015  # Should match quarterly_patches dictionary variable defined in vars/main.yml
* shutdown_listener: true # set to false if patching an empty oracle home (ie new 12c install)
* rollback_psu: false # set to true if rolling back current PSU.

### Required Inventory Variables

* oracle_install_type: valid values are WebLogic. 

* oracle_stage_install: directory that contains all oracle install files

* oracle_stage: directory to store logs and scripts used during playbook execution.

* oracle_version: expects values of 10.3.4 or 10.3.4

### Optional Inventory Variables

* None so far


## Example Playbook

    - hosts: servers
      roles:
         - role: psu-apply
