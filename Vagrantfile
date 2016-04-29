http_port = 8080

$install_python = <<SCRIPT
apt-get udpate
apt-get --assume-yes install python
SCRIPT

Vagrant.configure(2) do |config|

	config.vm.box = "ubuntu/xenial64"
	config.vm.network :forwarded_port, guest: 8080, host: http_port

	config.vm.provider :virtualbox do |vb|
		vb.customize ["modifyvm", :id, "--memory", "1024"]
		vb.customize ["modifyvm", :id, "--cpus", "2"]
	end

	config.vm.provision "shell", inline: $install_python
	config.vm.provision "ansible" do |ansible|
		ansible.playbook = "ansible/jenkins.yml"
	end

end
