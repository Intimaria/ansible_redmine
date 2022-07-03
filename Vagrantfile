Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/redmine.yml"
  end
end
