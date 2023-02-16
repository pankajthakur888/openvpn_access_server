Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
         
         
         
Issue Fix
---------
If not showing password 

Logs:- 

TASK [pankajthakur888.openvpn_access_server : Print OpenVPN Access Server password] ************************************************************
ok: [localhost] => {
    "openvpn_password.stdout_lines": []
}

OR

If Failed TASK Update and upgrade packages

Logs:- 

TASK [pankajthakur888.openvpn_access_server : Update and upgrade packages] *********************************************************************
[WARNING]: The value True (type bool) in a string field was converted to 'True' (type string). If this does not look like what you expect,
quote the entire value to ensure it does not change.
fatal: [localhost]: FAILED! => {"changed": false, "msg": "'/usr/bin/apt-get upgrade --with-new-pkgs ' failed: E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution).\n", "rc": 100, "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nYou might want to run 'apt --fix-broken install' to correct these.\nThe following packages have unmet dependencies:\n openvpn-as : Depends: python3-migrate but it is not installed\n              Depends: python3-sqlalchemy but it is not installed\n              Depends: python3-mysqldb but it is not installed\n              Depends: python3-cffi but it is not installed\n              Depends: python3-arrow but it is not installed\n              Depends: python3-lxml but it is not installed\n              Depends: python3-ldap3 but it is not installed\n              Depends: python3-defusedxml but it is not installed\n", "stdout_lines": ["Reading package lists...", "Building dependency tree...", "Reading state information...", "You might want to run 'apt --fix-broken install' to correct these.", "The following packages have unmet dependencies:", " openvpn-as : Depends: python3-migrate but it is not installed", "              Depends: python3-sqlalchemy but it is not installed", "              Depends: python3-mysqldb but it is not installed", "              Depends: python3-cffi but it is not installed", "              Depends: python3-arrow but it is not installed", "              Depends: python3-lxml but it is not installed", "              Depends: python3-ldap3 but it is not installed", "              Depends: python3-defusedxml but it is not installed"]}

PLAY RECAP *************************************************************************************************************************************
localhost                  : ok=1    changed=0    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0

Solution

       sudo apt --fix-broken install

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
