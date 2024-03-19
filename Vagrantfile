# -*- mode: ruby -*-
# vim: set ft=ruby :
#Path to HDD on host

Vagrant.configure(2) do |config|
  config.vm.box = "debian/bullseye64"
  config.vm.box_version = "11.20230615.1"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024 
    v.cpus = 1
  end
  
  config.vm.define "master" do |host|
    host.vm.hostname = "master"
    host.vm.network "private_network",
                     ip: "192.168.50.10",
                     adapter: 2
  end

  config.vm.define "slave" do |host|
    host.vm.hostname = "slave"
    host.vm.network "private_network",
                     ip: "192.168.50.11",
                     adapter: 2
    host.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/play.yml"
      ansible.inventory_path = "ansible/hosts"
      ansible.host_key_checking = "false"
      ansible.limit = "all"
    end

  end

end
