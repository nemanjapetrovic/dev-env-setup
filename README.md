# Setting up my development enviroment

## Requirment 

- Latest version of VirtualBox installed
- Latest version of VirtualBox extensions installed
- Putty
- Latest version of Vagrant installed

## Setting up vagrant machine

- Go to the [link](https://app.vagrantup.com/boxes/search) and search for Vagrant boxes
- My choice in this example will be *ubuntu/trusty32*
- In your ../Documents/Vagrant/ubuntu32/ folder run command: **vagrant box add ubuntu/trusty32**
- After Vagrant box is downladed in the same folder run command: **vagrant init**, just to mention Vagrant boxes are downloaded in ..Users/Username/.vagrant.d/boxes
- If you would like to change name of the Vagrant machine add this next lines to your "Vagrantfile"7
``` # Box name
  config.vm.define :master do |t|
  end
```
- Run command in your ../Documents/Vagrant/ubuntu32/ **vagrant up --provider=virtualbox**
- After command is finished your machine is good to go
- Open VirtualBox and click Settings on your machine
- Open Network tab and under Adapter 1 select "Attached to" : "Host-only Adapter" and under "Name":"{YOUR_VB_ADAPTER}"

## Setting up Putty

- Run VirtualBox machine and login to machine username/password : vagrant/vagrant
- Run command ifconfig
- Under et0 you will see an ip address, copy that address, "192.168.56.101" was tipically my address
- Open Putty and insert into Saved sessions new {SESSION_NAME}
- Insert ip addess you copied
- Under Logging (treeview on the left) select options you need, I typically select place where to store the log file and name of it
- Click button Save and your putty session will be saved
- Now create on desktop shortcut with "C:\Program Files\PuTTY\putty.exe" -ssh -load {SESSION_NAME}


