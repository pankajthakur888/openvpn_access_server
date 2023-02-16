Role Name
=========

The "pankajthakur888.openvpn_access_server" role is an Ansible role that installs the OpenVPN Access Server on Ubuntu. It updates and upgrades packages, installs required packages, downloads and installs the OpenVPN Access Server clients, creates an "openvpn" user with a random password, gets the OpenVPN Access Server password and restarts the OpenVPN Access Server service.

You can use this role in your Ansible playbooks to install the OpenVPN Access Server on Ubuntu servers in a repeatable and automated way.

Requirements
------------

In the case of the "pankajthakur888.openvpn_access_server" role, there are some requirements that need to be met before using it. The role assumes that the target `Ubuntu Server 20` has internet access and that the apt package manager is used to install packages.

Additionally, the sudo command should be available on the target server, and the user executing the Ansible playbook should have sufficient permissions to run the commands in the role.

It is also assumed that the target server meets the minimum requirements for running the OpenVPN Access Server. Please refer to the OpenVPN Access Server documentation for more information on system requirements.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

If the "pankajthakur888.openvpn_access_server" role has any dependencies on other roles or packages, it should be mentioned in the role's documentation.

However, in this case, the role does not have any dependencies on other roles or packages.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
         

How To Run
-----------

To run the "pankajthakur888.openvpn_access_server" role, you will need to include it in your Ansible playbook. You can do this by creating a playbook YAML file that includes the following:

File:- Deploy_openvpn.yml

    - name: Install OpenVPN Access Server
      hosts: your_target_server
      become: yes
      roles:
        - role: pankajthakur888.openvpn_access_server

Commands
    
    sudo su

    ansible-galaxy install pankajthakur888.openvpn_access_server
    
    cd /root/.ansible/roles/pankajthakur888.openvpn_access_server
    
    ansible-playbook Deploy_openvpn.yml
    
    systemctl status openvpnas
         
         
         
Issue Fix
---------
If not showing password 

Logs:- 


![image](https://user-images.githubusercontent.com/45850188/219280613-b8e0b127-a7f4-41ea-89a0-3ce896526d1a.png)

OR

If Failed TASK Update and upgrade packages

Logs:- 


![image](https://user-images.githubusercontent.com/45850188/219280146-326f932a-ea47-4990-a917-d8e962e1e87c.png)


Solution
--------

       sudo apt --fix-broken install
       
Check Service

       sudo systemctl status openvpnas
       
       
NOTE
----

To access the OpenVPN Access Server Admin Web UI, you can go to https://<server-ip-address>/admin in your web browser.

Make sure to replace <server-ip-address> with the actual IP address of your OpenVPN server.

You should be prompted to enter the admin credentials during the first login. By default, the username is "openvpn" and the password can be obtained from the playbook output, which should have printed the password for the openvpn user.


License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
