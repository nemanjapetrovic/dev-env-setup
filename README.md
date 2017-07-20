# Setting up my development environment

## Requirments

- Latest version of VirtualBox installed
- Latest version of VirtualBox extensions installed
- Latest version of Vagrant installed
- Putty

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

## Setting up Putty

- Run VirtualBox machine and log in to machine username/password: vagrant/vagrant
- Run command ```ifconfig```
- Under eth0 you will see an IP address, copy it, example: "192.168.56.101"
- Open Putty and insert into Saved sessions new {SESSION_NAME}
- Insert IP address you copied
- Under Logging (tree view on the left) select options you need, I typically select place where to store the log file and name of it
- Click button Save and your putty session will be saved
- Now create on desktop shortcut to ```"C:\Program Files\PuTTY\putty.exe" -ssh -load {SESSION_NAME}```


