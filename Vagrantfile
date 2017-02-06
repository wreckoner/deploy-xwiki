Vagrant.configure("2") do |config|
	config.vm.box = "ubuntu/xenial64"
	config.vm.network "private_network", ip: "192.168.56.10"
	config.vm.network :forwarded_port, guest: 8443, host: 8443
	config.vm.provider "virtualbox" do |vb|
		vb.name = "xwiki"
		vb.memory = "2048"
	end
	config.vm.provision "shell", inline: "apt update"
	config.vm.provision "shell", inline: "apt -y install python"
	config.vm.provision "ansible" do |ansible|
		ansible.playbook = "xwiki.yml"
	end
end
