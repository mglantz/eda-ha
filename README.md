Role Name
=========

A role which provides high availability for a Event Driven Ansible server.
For more details see: https://github.com/mglantz/eda-ha/

Requirements
------------

Create the file: /var/lib/ansible-automation-platform/eda/ui/static/media/detect.json on each EDA server, as follows:
```
{
   "install_id": "unique_id_that_you_make_up_fqdn_perhaps"
}
```

Role Variables
--------------

load_balancer_fqdn: <string|fqdn of load balancer> 
eda_fqdn: <string|fqdn of eda server>

Dependencies
------------

An installed instance of https://github.com/ansible/eda-server

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
- name: Event-driven action playbook
  hosts: all
  roles:
    - { role: eda-ha, load_balancer_fqdn: "loadbalancer.sudo.net", eda_fqdn: "eda.sudo.net" }
  tasks:
    - name: Fix web server if event detects it broken
      ansible.builtin.debug:
        msg: "Imaginary fix"
      when: eda_activation
    - name: Do something else
      ansible.builtin.debug:
        msg: "Imaginary something else"
      when: eda_activation
```

License
-------

GPL 3.0

Author Information
------------------

Magnus Glantz, sudo at redhat.com, 2023
