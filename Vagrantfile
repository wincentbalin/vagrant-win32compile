# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty32"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false     # we log into here using ssh
    vb.cpus = "4"      # my computer has that many
    vb.memory = "3072" # we use a 32-bit OS here, but we max out RAM
    vb.customize ["modifyvm", :id, "--ioapic", "on"] # 32-bit multi-CPU guest needs it on a 64-bit host
  end
  
  # Install mingw32 compiler and a couple of utilities
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
	apt-get upgrade -y
	apt-get install -y mingw32 pkg-config bison flex nasm
	apt-get install -y vim mc screen
	ln -sf /vagrant /home/vagrant/host
  SHELL
end
