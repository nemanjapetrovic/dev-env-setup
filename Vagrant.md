# Setting up my development environment

## Requirments

- Latest version of VirtualBox installed
- Latest version of VirtualBox extensions installed
- Latest version of Vagrant installed

## Downloading Vagrant box

- Go to the [link](https://app.vagrantup.com/boxes/search) and search for Vagrant boxes
- My choice in this example will be *ubuntu/trusty32*
- Create somewhere folder where some *Vagrantfile* will be stored
- Inside that folder (in future text *vagrant-folder*) run cmd with command: ```vagrant box add ubuntu/trusty32```
- After Vagrant box is downloaded it's stored in ../Users/{USERNAME}/.vagrant.d/boxes

## Setting up Vagrant machine

- First, open *vagrant-folder* and run in cmd command: ```vagrant init``` this will create *Vagrantfile*
- If you would like to change name of the Vagrant machine add next lines to your "Vagrantfile"
``` 
# Box name
config.vm.define :master do |t|
end
```
- Now run in the same folder cmd command: ```vagrant up --provider=virtualbox``` this will bind Vagrant box to your Oracle Virtual Box
- After command is finished your machine is good to go
- Open VirtualBox and click Settings on your machine
- Open Network tab and under *Adapter 1* select "Attached to" : "Host-only Adapter" and under "Name":"{YOUR_VB_ADAPTER}"
- Next time you want to run machine just open vagrant-folder and run in cmd ```vagrant up```
