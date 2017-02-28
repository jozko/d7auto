# d7auto
Ansible roles to auto install Drupal with Civicrm

## Usage

* Copy vars/site.yml to var/site.local.yml
* Fill out the site domain info, passwords
* You can use the Vagrant file provided with the Ansible playbooks to start local Vagrant VM
* Update the hosts.txt file accordingly
* Run Ansible using ```ansible-playbook -i hosts.txt site.yml```
