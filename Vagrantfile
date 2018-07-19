# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

 config.vm.box = "centos/7"


 config.vm.provider "virtualbox" do |vb|
   vb.memory = "1024"
 end


 config.vbguest.auto_update = false
 config.vbguest.no_install = false
 config.vbguest.no_remote = true

 config.vm.hostname = "jenkins"
 


 config.vm.synced_folder "vagrant", "/vagrant", :mount_options => ["ro"]


 config.vm.provision "ansible_local" do |ansible|
   ansible.provisioning_path = "/vagrant/provisioning"
   ansible.inventory_path = "inventory"
   ansible.playbook = "playbook.yml"
   ansible.limit = "all"
 end

end