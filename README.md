# auriga-vagrant
## Description
Auriga local vagrant and ansible provisioning files.  
The image is for build and run enviroment.  
Image needs to edit synced_folder setting for Vagrantfile.

## Requirement
*  virtualbox
*  vagrant
*  ansible

### Install requirement tools
**For OSX users**  
```
$ brew install ansible
$ brew tap caskroom/cask
$ brew install brew-cask
$ brew cask install virtualbox
$ brew cask install vagrant
```

## Installation
1. git clone https://github.com/poporing-popori/auriga-vagrant.git
2. cd auriga-vagrant
3. vagrant up

## Configuration
Edit Vagrantfile the synced_folder setting:  
`config.vm.synced_folder "~/auriga", "/opt/auriga", type: :nfs`  
Your auriga directory path set the `~/auriga`.

## Run Vagrant
run:  
```
$ vagrant up
```
If vagrant need password when input your root password.

## Configuration Auriga
* /opt/auriga/Makefile
```
# Your client matching version
# e.g.
PACKETVER=20150513
```
* /opt/auriga/conf/char_auriga.conf
```
# Setting the character server ip
char_ip: 192.168.33.10
char_port: 6121
```
* /opt/auriga/conf/map_auriga.conf
```
# Setting the map server ip
map_ip: 192.168.33.10
map_port: 5121
```
* Put the GRF file and editing grf-files.txt

## Run Auriga
run:
```
$ vagrant ssh
$ cd /opt/auriga
$ make sql
$ sh auriga-start start
```