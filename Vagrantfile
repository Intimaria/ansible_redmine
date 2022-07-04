Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/provision.yml"
  end
end
