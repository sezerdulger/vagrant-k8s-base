# -*- mode: ruby -*-
# vi: set ft=ruby :
MASTER_NODE_IP_START="192.168.40.1"
SLAVE_NODE_IP_START="192.168.40.2"

JOIN_TOKEN="abcdef.1234567890123456"
WORKER_COUNT=1
Vagrant.configure("2") do |config|
  

  config.vm.define "base" do |node|
      node.vm.box = "ubuntu/xenial64"
	  node.vm.hostname = "ubuntu"
      #node.vm.box_version = "0"
      #node.vm.network "forwarded_port", guest: 7077, host: 21001, host_ip: "127.0.0.1"
      
      node.vm.network "private_network", ip: "192.168.40.30"
      node.vm.synced_folder "data", "/data"
      
	  node.vm.provision "shell", path: "data/install.sh", args: "install"
      
	  node.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
		vb.cpus = 1
	  end
    end
	
	
end


