
# CentOS 7 (1511) for Vagrant

## Set up for CentOS 7
  * new virtualbox
  * disable audio
  * disable usb

## Install centos7
  * language: English
  * DATE and Time: Asia/Tokyo
  * INSTLLATION DESTINATION: ATA VBOX HARDDISK
  * NETWORK and HOST NAME: Ethernet (enpOs3) ON
  * ROOT PASSWORD: vagrant

## Setup centos7
```bash
# sed -i "s/^.*requiretty/#Defaults requiretty/" /etc/sudoers
# yum -y install gcc make gcc-c++ kernel-devel-`uname -r` zlib-devel openssl-devel readline-devel sqlite-devel perl wget dkms nfs-utils vim bzip2
# echo "UseDNS no" >> /etc/ssh/sshd_config
# /usr/sbin/groupadd vagrant
# /usr/sbin/useradd vagrant -g vagrant -G wheel
# echo "vagrant"|passwd --stdin vagrant
# echo "vagrant        ALL=(ALL)       NOPASSWD: ALL" >> /etc/sudoers.d/vagrant
# chmod 0440 /etc/sudoers.d/vagrant
# mkdir -pm 700 /home/vagrant/.ssh
# wget --no-check-certificate 'https://raw.github.com/mitchellh/vagrant/master/keys/vagrant.pub' -O /home/vagrant/.ssh/authorized_keys
# chmod 0600 /home/vagrant/.ssh/authorized_keys
# chown -R vagrant /home/vagrant/.ssh
# mount /dev/cdrom /mnt
# sh /mnt/VBoxLinuxAdditions.run
# umount /mnt
```

## Make Vagrant box
```bash
$ vagrant --base centos7 --output centos7minimal.box
$ vagrant box add centos7minimal centos7minimal.box
$ mkdir centos7minimal
$ cd centos7minimal
$ vagrant init centos7minimal
$ vagrant up
$ vagrant ssh
$ vagrant halt
```

## Update Guest Additions

```bash
$ vagrant plugin list
$ vagrant plugin install vagrant-vbguest
$ vagrant vbguest
```

## Desktop

```bash
$ sudo yum -y groupinstall "GNOME Desktop" 
$ sudo systemctl set-default graphical.target
$ systemctl get-default
graphical.target
```
