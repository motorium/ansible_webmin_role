Role Name
=========

Ansible role to deploy Webmin web-based linux administration utility, running as a 
systemd service.

Webmin service will be available on https://hostip:10000.

Default login will be the userid and password of the installer user.

You may get a browser warning about Webmin's default self-sign SSL certificate.


Requirements
------------

Requires root privileges.

Role Variables
--------------

- `install_utilities`: false

Set to True to install various utility packages used by Webmin management functions (wget, git, ntpdate, sntp, smartmontools)

- `firewalld_enable`: false

Set to True to open port 10000 via firewalld (assumes firewalld is running)

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml

    - name: Provision webmin role
      hosts: all
      become: true
      become_user: root
      
      vars:
         firewalld_enable: false
         install_utilities: true

      roles:
      - semuadmin.webmin
```
     
License
-------

BSD

Author Information
------------------

semuadmin@noreply.user.github.com
