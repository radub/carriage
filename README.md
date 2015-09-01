# Carriage

Bare-bones VirtualBox + Vagrant + Chef-Solo VM spin-up

# Package details

- contains vm spin-up configuration and provisioning using chef-solo
- before spining up the VM you might want to check the Vagrant file for any configurations of your own you might want to change (ex: vm name)
- the cookbooks used for provisioning reside in /devops/chef/cookbooks as git submodules provided by OpsCode https://github.com/opscode-cookbooks
- boxes are being downloaded from http://opscode-vm-bento.s3.amazonaws.com/

# Prerequisites

0. Mac OS X - 10.9.3
1. Chef Development Kit (tested on 0.1.0 - http://www.getchef.com/downloads/chef-dk)
2. Vagrant (tested on v 1.6 - http://www.vagrantup.com/downloads.html)
3. VirtualBox (tested on v4.3.12 - https://www.virtualbox.org/wiki/Downloads)

## Vagrant plugins

vagrant-omnibus
```
$ vagrant plugin install vagrant-omnibus
```

vagrant-berkshelf
```
$ vagrant plugin install vagrant-berkshelf --plugin-version 2.0.1
```

## Tested versions

```
$ ruby --version
# ruby 2.0.0p451 (2014-02-24 revision 45167) [universal.x86_64-darwin13]

$ vagrant plugin list
# vagrant-berkshelf (2.0.1)
#   - Version Constraint: 2.0.1
# vagrant-login (1.0.1, system)
# vagrant-omnibus (1.4.1)
# vagrant-share (1.0.1, system)

$ berks --version
# 3.1.1

$ chef-solo --version 
# Chef: 11.14.0.alpha.1
```

# Setup

#### 1. Get the stuff

```  
# clone the repo
$ git clone https://github.com/radub/vm.git .

# add the submodules
$ git submodule update --init --recursive
  
# after adding the submodules you may pull the submodule latest updates
$ git submodule foreach git pull origin master
$ berks update
```

#### 2. Spin-up the VM

```  
$ vagrant up
```



