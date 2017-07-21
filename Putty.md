## Setting up Putty session

- Run VirtualBox machine and log in to linux machine username/password: vagrant/vagrant
- Run command ```ifconfig```
- Under eth0 you will see an IP address, copy it, example: "192.168.56.101"
- Open Putty and insert into Saved sessions new {SESSION_NAME}
- Insert IP address you copied
- Under Logging (tree view on the left) select options you need, I typically select place where to store the log file and name of it
- Click button Save and your putty session will be saved
- Now create on desktop shortcut to ```"C:\Program Files\PuTTY\putty.exe" -ssh -load {SESSION_NAME}```
