# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	3.times do |n|
		config.vm.define "node"+(1+n).to_s do |cc|
					cc.vm.host_name = "node" + (1+n).to_s
					cc.vm.network :private_network, ip: "10.10.10.1" + n.to_s
					if cc.vm.hostname == "node1" then
						 cc.vm.box = "centos/7"
						 cc.vm.box_check_update = true
						 cc.vm.network "forwarded_port", guest: 3306, host: 3307
						 cc.vm.provider :virtualbox do |vb|
								vb.gui = false
								vb.memory = "1024"
								vb.name = "node"+(1+n).to_s
						end
					end
					if cc.vm.hostname == "node2" then
						 cc.vm.box = "centos/7"
						 cc.vm.box_check_update = true
						 cc.vm.network "forwarded_port", guest: 3306, host: 3308
						 cc.vm.provider :virtualbox do |vb|
								vb.gui = false
								vb.memory = "1024"
								vb.name = "node"+(1+n).to_s
						end
					end
					if cc.vm.hostname == "node3" then
						 cc.vm.box = "centos/7"
						 cc.vm.box_check_update = true
						 cc.vm.network "forwarded_port", guest: 8989, host: 8989
						 cc.vm.provider :virtualbox do |vb|
								vb.gui = false
								vb.memory = "1024"
								vb.name = "node"+(1+n).to_s
						end
					end
		end
	end
end
