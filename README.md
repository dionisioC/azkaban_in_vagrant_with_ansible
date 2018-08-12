# azkaban in vagrant with ansible

# Objective

The objective of this repo is have an easy installation of azkaban
using ansible and vagrant.
It is the solo version using mysql

# Sources

As this is the first time I use ansible, and I am not an expert, I
checked the following repos:

https://github.com/wolfosis/Azkaban

https://github.com/amirhhz/azkaban-ansible-vagrant

Also I checked the official ansible documentation

https://docs.ansible.com/

# Requirements

Ansible and vagrant are required. Installation steps are provided below


## Install ansible locally (ubuntu)
```
sudo apt-get update
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

## Install vagrant locally (ubuntu)

```
wget https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_x86_64.deb
wget https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_SHA256SUMS
wget https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_SHA256SUMS.sig
wget https://keybase.io/hashicorp/key.asc
gpg --import key.asc
gpg --verify vagrant_2.1.2_SHA256SUMS.sig  vagrant_2.1.2_SHA256SUMS
apt install ./vagrant_2.1.2_x86_64.deb
vagrant plugin install vagrant-vbguest
```


# Usage

clone the repo

```
git clone git@github.com:dionisioC/azkaban_in_vagrant_with_ansible.git
```

Go inside the folder

```
cd azkaban_in_vagrant_with_ansible
```

Run vagrant

```
vagrant up
```


Go to your web browser

```
http://localhost:8081/
```