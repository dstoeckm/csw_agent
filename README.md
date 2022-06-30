Role Name
=========

this collection of Ansible roles is intended to install, delete or update a Cisco Secure Workload Agent on a remote machine.

Requirements
------------

to install the agent into the right context admins need to have the name of the Tenant available and an inventory file as a list of IP addresses:

10.1.96.10
10.1.89.15

a sample version is provided also.

Role Variables
--------------

there are no addition variables needed

Dependencies
------------

The .sh installer for each Tenant need to be pushed into the file folder under the role of "cws-install" and "csw-upgrade" the {{ csw_tenant }} variable will be used to indentify the Tenant. as example: the installation script for the tenant duslab is use to install by this scrip tetration_installer_duslab_enforcer_linux.sh. So the admin need to push the installer script into roles/csw-install/files and roles/csw-upgrade/files .
executing the Playbook, there will be an interactive question regarding the Tenant.

To have the right format of the CSW access key / secret, copy the CSW_access-all.yml-.example to all.yml in the group_vars folder and edit your information.

Example Playbook
----------------

To install the agent to a list of server, the admin needs to execute the playbook like this:
"ansible-playbook csw-install.yml -i inventory"

the difference between "csw-delete" and "csw-delete-all" is the deletion of all files and folder and remove the agent from the cluster in the "csw-delete-all" version. the "csw-delete" version will keep all cert folders to identify the agent and will not remove the agent from the cluster.

License
-------

BSD

Author Information
------------------

If you have any question you can contact my @dstoeckm on twitter
