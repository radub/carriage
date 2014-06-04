# The VM

VirtualBox + Vagrant + Chef-Solo VM spinup

# Package details

- contains vm spinup configuration and provisioning using chef-solo
- before spining up the VM you might want to check the Vagrant file for any configurations of your own you might want to change
- the cookbooks used for provisioning reside in /devops/chef/cookbooks as git submodules provided by OpsCode https://github.com/opscode-cookbooks
- boxes are being downloaded from http://opscode-vm-bento.s3.amazonaws.com/

# Prerequisites

1. Chef Development Kit (tested on 0.1.0 - http://www.getchef.com/downloads/chef-dk)
2. Vagrant (tested on v 1.6)
3. VirtualBox (tested on v4.3.12)

## Vagrant plugins

vagrant-omnibus
```
$ vagrant plugin install vagrant-omnibus
```

vagrant-berkshelf
```
$ vagrant plugin install vagrant-berkshelf --plugin-version 2.0.1
```

# Setup

#### 1. Clone the repo

```  
$ git clone https://github.com/radub/vm.git .
$ git submodule update --init --recursive
  
# after adding the submodules you may pull the submodule latest updates:
  
$ git submodule foreach git pull origin master
```

#### 2. VM Spin-up

```  
$ vagrant up
```



