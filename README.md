# The VM

VirtualBox + Vagrant + Chef-Solo VM spinup

## Package details

- contains vm spinup configuration and provisioning using chef-solo
- before spining up the VM you might want to check the Vagrant file for any configurations of your own you might want to change
- the cookbooks used for provisioning reside in /devops/chef/cookbooks as git submodules provided by OpsCode (https://github.com/opscode-cookbooks)

## Prerequisites

Vagrant 1.6

Vagrant plugins:
- vagrant-omnibus
```
vagrant plugin install vagrant-omnibus
```

VirtualBox 4.3.10

## Setup

1. Clone repo
  
  $ git clone https://github.com/radub/vm.git .
  
  $ git submodule update --init --recursive
  
  after adding the submodules you may pull the submodule latest updates:
  
  $ git submodule foreach git pull origin master

2. VM Spin-up
  
  $ vagrant up
