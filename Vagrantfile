# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.network "public_network"
  config.vm.synced_folder "~", "/vagrant_data"

  config.vm.define :dev do |t| 
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook/dev.yml"
    end 
  end
  config.vm.provider :virtualbox do |vb|
  vb.name = "dev"
  end
end
