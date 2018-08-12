# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"
  config.vm.hostname = "azkaban"
  config.ssh.insert_key = false

  config.vm.network "forwarded_port", guest: 8081, host: 8081, host_ip: "127.0.0.1"

  config.vm.synced_folder "./data", "/vagrant_data", SharedFoldersEnableSymlinksCreate: false

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "4096"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "azkaban.yml"
  end

end
