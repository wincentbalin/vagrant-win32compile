# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty32"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false     # we log into here using ssh
    vb.cpus = "4"      # my computer has that many
	vb.ioapic = "on"   # 32-bit multi-CPU guest needs it on a 64-bit host
    vb.memory = "3072" # we use a 32-bit OS here, but we max out RAM
  end
  
  # Install mingw32 compiler and a couple of utilities
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
	apt-get upgrade -y
    apt-get install -y mingw32 pkg-config bison flex nasm
	apt-get install -y vim mc screen
  SHELL
end
