# azkaban_in_vagrant_with_ansible
Installing azkaban in a virtual machine using vagrant and ansible

Trying to install azkaban in a virtual machine using vagrant and ansible

# Checking 

https://github.com/wolfosis/Azkaban
https://github.com/amirhhz/azkaban-ansible-vagrant


# Install ansible locally (ubuntu)

sudo apt-get update
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible

# Install vagrant locally (ubuntu)


dio@linux:~/vagrant_install$ wget https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_x86_64.deb
--2018-07-29 10:28:59--  https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_x86_64.deb
Resolving releases.hashicorp.com (releases.hashicorp.com)... 151.101.1.183, 151.101.65.183, 151.101.129.183, ...
Connecting to releases.hashicorp.com (releases.hashicorp.com)|151.101.1.183|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43525726 (42M) [application/x-debian-package]
Saving to: ‘vagrant_2.1.2_x86_64.deb’

vagrant_2.1.2_x86_6 100%[===================>]  41,51M  35,4MB/s    in 1,2s    

2018-07-29 10:29:01 (35,4 MB/s) - ‘vagrant_2.1.2_x86_64.deb’ saved [43525726/43525726]

dio@linux:~/vagrant_install$ ll
total 42536
drwxr-xr-x  2 dio dio     4096 jul 29 10:28 ./
drwx------ 38 dio dio    12288 jul 29 10:29 ../
-rw-r--r--  1 dio dio 43525726 jun 26 22:42 vagrant_2.1.2_x86_64.deb
dio@linux:~/vagrant_install$ wget https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_SHA256SUMS
--2018-07-29 10:30:54--  https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_SHA256SUMS
Resolving releases.hashicorp.com (releases.hashicorp.com)... 151.101.1.183, 151.101.65.183, 151.101.129.183, ...
Connecting to releases.hashicorp.com (releases.hashicorp.com)|151.101.1.183|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 821 [text/plain]
Saving to: ‘vagrant_2.1.2_SHA256SUMS’

vagrant_2.1.2_SHA25 100%[===================>]     821  --.-KB/s    in 0s      

2018-07-29 10:30:54 (85,6 MB/s) - ‘vagrant_2.1.2_SHA256SUMS’ saved [821/821]

dio@linux:~/vagrant_install$ wget https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_SHA256SUMS.sig
--2018-07-29 10:31:09--  https://releases.hashicorp.com/vagrant/2.1.2/vagrant_2.1.2_SHA256SUMS.sig
Resolving releases.hashicorp.com (releases.hashicorp.com)... 151.101.193.183, 151.101.1.183, 151.101.65.183, ...
Connecting to releases.hashicorp.com (releases.hashicorp.com)|151.101.193.183|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 310 [application/octet-stream]
Saving to: ‘vagrant_2.1.2_SHA256SUMS.sig’

vagrant_2.1.2_SHA25 100%[===================>]     310  --.-KB/s    in 0s      

2018-07-29 10:31:09 (34,3 MB/s) - ‘vagrant_2.1.2_SHA256SUMS.sig’ saved [310/310]

dio@linux:~/vagrant_install$ wget https://keybase.io/hashicorp/key.asc 
--2018-07-29 10:34:35--  https://keybase.io/hashicorp/key.asc
Resolving keybase.io (keybase.io)... 52.6.136.121, 52.55.1.130
Connecting to keybase.io (keybase.io)|52.6.136.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1714 (1,7K) [text/plain]
Saving to: ‘key.asc’

key.asc             100%[===================>]   1,67K  --.-KB/s    in 0s      

2018-07-29 10:34:36 (151 MB/s) - ‘key.asc’ saved [1714/1714]

dio@linux:~/vagrant_install$ gpg --import key.asc 
gpg: key 51852D87348FFC4C: public key "HashiCorp Security <security@hashicorp.com>" imported
gpg: Total number processed: 1
gpg:               imported: 1

dio@linux:~/vagrant_install$ gpg --verify vagrant_2.1.2_SHA256SUMS.sig  vagrant_2.1.2_SHA256SUMS
gpg: Signature made mié 27 jun 2018 18:59:06 CEST
gpg:                using RSA key 91A6E7F85D05C65630BEF18951852D87348FFC4C
gpg: Good signature from "HashiCorp Security <security@hashicorp.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 91A6 E7F8 5D05 C656 30BE  F189 5185 2D87 348F FC4C

dio@linux:~/vagrant_install$ apt install ./vagrant_2.1.2_x86_64.deb
