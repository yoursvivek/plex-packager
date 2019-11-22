# plex-packager
Plex Packager for WD My Cloud (Gen 2)

## Pre-requisites and Installation
Plex Packager uses _Vagrant_ and _Virtual Box_ to repackage Plex Media Server. 


Once you have `vagrant` ready, simply clone this repository.

```
git clone https://github.com/yoursvivek/plex-packager
```

## Usage

```
# change directory to plex-packager
cd plex-packager
# start your VM
vagrant up
# ssh into your VM
vagrant ssh
# run plex-packager inside the VM
plex-packager
# exit
exit
# Your binaries will be found inside `target` directory.
# Don't forget to halt the VM
vagrant halt
```
