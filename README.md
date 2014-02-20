vm
==

VirtualBox + Vagrant + Chef-Solo VM spinup

Package details

- contains vm spinup configuration and provisioning using chef-solo
- before spining up the VM you might want to check the Vagrant file for any configurations of your own you might want to change
- the cookbooks used for provisioning reside in /devops/chef/cookbooks as git submodules
- devops/misc/permissions.sh is not realy in the scope of this basic package but you might find it usefull if you want to develop a Drupal project

Setup

1. Clone repo
  $ git clone https://github.com/radub/vm.git .
  $ git submodule update --init --recursive

2. VM Spin-up
  $ vagrant up
