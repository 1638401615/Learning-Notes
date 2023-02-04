## use ssh to connect remote machine

### intro to ssh 

-  secure shell is a community protocol where traffic encrypted
-  ssh is the client, sshd(ssh daemon) is the server. the server must have sshd installed and running so it can be connected by ssh

### generate ssh-keys and copy it to remote

use `ssh-keygen` to create a key pair in Users/anyu/.ssh

to copy the public keys to the remote machine:

`cat .ssh/id_rsa.pub | ssh -p port anyu@ip "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >> ~/.ssh/authorized_keys"`

### other useful operation

to copy or move files of local machine to a remote machine: 

`scp dirpath_local anyu@ip:dirpath_remote`

when generated a new key, you should run `ssh-add new_key` to add it into Identification

## configure the remote machine

### update and upgrade the apt
```shell
sudo apt update
sudo apt upgrade
```

### add user and stop the root user
use `adduser anyu` to add a user anyu

use `id anyu` to show the info of anyu

`usermod -aG sudo anyu` to give privilege to anyu

*but at this time, `ssh anyu@ip` will fail, we need to add public key to /home/anyu/.ssh/authorized_keys*

to stop the root user, change the config file `etc/ssh/sshd_config`, and set `PermitRootLogin` to `no`

finally, run `sudo systemctl reload sshd`

## add remote to ssh of github
### change group of .ssh

currently, the *.ssh* has the group *root:root*, we should change it to *anyu:anyu* before we generate a new ssh-keys for github, we can use the command below:

`sudo chown -R anyu:anyu /home/anyu/`

```shell
ssh-keygen -t rsa
eval 'ssh-agent -s'
ssh-add /home/anyu/.ssh/id_rsa_name.pub
```