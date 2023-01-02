Apigee Central Repo
===========================

This repo provides various ansible roles for Google Apigee product. 

Playbooks
------------
Upgrade/Install:
    - Playbook to automate apigee componenets install. It can install/upgrade any apigee topology depending on how your inventory file is setup.

Server Migration:
    - Migrating components off of an old server to a new server, serially. It will uninstall ipa on both servers and reuse the old server ip along with syncing the data. Since in the backend apigee uses ip address (zookeeper) for its configuration this processes will make sure that the migration is seemless. 

Requirements
------------
Upgrade/Install:
    - Access to apigee user/password software repo
    - Response file placed on all servers 

Server Migration:
    - Root Access to all servers

Roles
------------

| Role Name | Description |
| --- | --- |
| bootstrap | Download & Install bootstrap file |
| component-install | Install apigee components |  
| componenet-upgrade | Upgrade apigee components |
| utils/ipa-uninstall | Uninstall ipa & reuse ip from old server to new server|  
| utils/rsync | Rsync apigee directory |
| utils/stop-apigee | apigee-all stop |

 
Role Variables
--------------
Default values for these variables are provided by the role apigee-opdk-setup-default-settings. The variables used in 
this role are:

| Variable Name | Description |
| --- | --- |

| opdk_user_name | System user name. Set to `apigee` |  
| opdk_group_name | System group name. Set to `apigee` |
| bootstrap_file_path | Path to the bootstrap script |
| apigee_version is Version of OPDK to install |
| apigee_repo_user | Apigee repository user name for https://software.apigee.com |
| apigee_repo_password | Apigee repository user password for https://software.apigee.com |
| http_proxy | HTTP Proxy url that should be used to get online |
| https_proxy | HTTPS Proxy url that should be used to get online |
| no_proxy | Domains or IPs that should not be proxied | 
| old_server | Name/ip of server that you need to migrate |        


Example Playbook
----------------
