# Ansible SVI Migration Playbook
## Shut down SVIs on Nexus switches and bring up Unicast Routing on ACI


### USAGE:
1. Create the files n7k-password.yml and aci-password.yml in the following format:

```
username: <YOUR USERNAME>
password: <YOUR PASSWORD>
```
2. Encrypt the password files using Ansible Vault:

```
ansible-vault encrypt n7k-password.yml
ansible-vault encrypt aci-password.yml
```
3. Populate the VLANs to be shut down on the Nexus, and unicast-enabled on ACI.  
Note that this assumes BDs named in the format "VLANX" where X = the VLAN number. 

4. Run the playbook.
```
ansible-playbook svi-migrate.yml -i hosts --ask-vault
```
