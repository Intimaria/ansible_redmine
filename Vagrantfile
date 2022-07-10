Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/provision.yml"
  end
end
