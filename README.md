Role Name
=========

Role to backup components of ansible controller.

Requirements
------------

ansible.controller collection is needed to use the role, the role could be changed to awx.awx and still work

Role Variables
--------------
* used throughout role
controller_host - variable giving a controller host to connect to
controller_user - controller login user with admin privledges
controller_pass - controller password for controller_user above

* set in defaults, change in playbook if needed
validate_certs: false
config_location: ./configs


Dependencies
------------

ansible.controller 

The role could be changed to use awx.awx and still work

Example Playbook
----------------


---
- name: Backup Ansible controller
  hosts: localhost
  connection: local
  vars:
    controller_hostname: "{{ controller_host }}"
    controller_username: "{{ controller_user }}"
    controller_password: "{{ controller_pass }}"
    # Set in role defaults
  #validate_certs: false
  #config_location: ./configs
  vars_files: vault.yml
  roles:
    - backup_controller


License
-------

BSD

Author Information
------------------

