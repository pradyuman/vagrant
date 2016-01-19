# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
	# Base Box
	config.vm.box = "ubuntu/trusty64"

	# Connect to IP
	config.vm.network :private_network, ip: "192.168.99.1"

	#Forward to Port
	#config.vm.network :forwarded_port, guest:80, host: 9000
	
	#Hardware Configuration
	config.vm.provider :virtualbox do |v|
		#RAM
		v.customize ["modifyvm", :id, "--memory", "4096"]

		#Multicore
		v.customize ["modifyvm", :id, "--cpus", "2"]
		v.customize ["modifyvm", :id, "--ioapic", "on"]
	end

	#Provisioning Script
	config.vm.provision "shell", path: "init.sh"

	"Synced Folders
	config.vm.synced_folder "./data", "/host/", "mount_options" => [ "dmode=777", "fmode=666" ]

end
