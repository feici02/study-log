## How to use vagrant on macOS?

### 1. install
```
# default provider
brew cask install virtualbox

brew cask install vagrant
```

### 2. vagrant commands
```
mkdir vagrant-getting-started
cd !$

vagrant version

# Vagrantfile will be created at current dir
vagrant init hashicorp/precise64

# start the VM
# shared folders: /vagrant on the VM is liked to current dir
vagrant up

# log in the VM
vagrant ssh

# suspend the VM
vagrant suspend

# check the status of the VM
vagrant status

# resume suspended VM
vagrant resume

# shutdown the VM
vagrant halt

# remove the VM from virtualbox
vagrant destroy

# list installed boxes
vagrant box list
```
