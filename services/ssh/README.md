# SSH server configuration
This image copies the contents of src/resources/authorized_keys to /root/.ssh/authorized_keys.

By default, that file is a softlink to ${HOME}/.ssh/id_rsa.pub, so when you build a container, the private key from that machine can log into the container as root. If you want to add more users, cat the contents of their id_rsa.pub files into a single file, separated by line breaks, and replace the soft link with a real file.

# building the container
``` bash
make
```

# running the container
``` bash
./Runfile
```

# connecting to the container
Assuming you are building from scratch and have already set up your ssh keys, you can ssh to the container as root.

``` bash
ssh root@172.0.1.2
```
If you have multiple docker containers running, you will need to determine which one is running the ssh server. If you source the conopsrc file at the root of this repository, you should have a function that will list docker containers and their ip addresses.

