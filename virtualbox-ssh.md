### [How to SSH to a VirtualBox guest externally through a host?](https://stackoverflow.com/questions/5906441/how-to-ssh-to-a-virtualbox-guest-externally-through-a-host)

`VBoxManage modifyvm myserver --natpf1 "ssh,tcp,,3022,,22"`

`ssh -p 3022 user@localhost`

### [Run VirtualBox in background, without a window?](https://superuser.com/questions/135498/run-virtualbox-in-background-without-a-window)

`VBoxManage startvm $VM --type headless`

Then use ssh to connect your vm.

### shutdown

Guest send `shut down` the vm will be scheculed to shutdown in one minute.

