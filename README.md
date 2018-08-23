# Ansible playbook to install Gitlab into AWS

I created this playbook for our needs to quickly provision Gitlab into AWS
for our Ansible roadshow. I save it here for further needs.

# Usage

1. Edit vars/main.yml for your needs
2. add vars/vault.yml to have your AWS creds (there is example)
3. set boto for aws keys too
4. add vault-password.txt file
5. to install, run:
  1. ```ansible-vault --vault-password-file vault-password.txt encrypt vars/vault-example.yml```
  2. ```ansible-playbook --vault-password-file vault-password.txt -i inventory/ec2.py do_all.yml```
6. To decommission the instance, run:
  1. ```ansible-playbook --vault-password-file vault-password.txt -i inventory/ec2.py delete_instances.yml```
