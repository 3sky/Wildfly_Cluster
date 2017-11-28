# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "debian/jessie64"
  config.vm.define "myserver1" do |myserver1|
   myserver1.vm.hostname = "myserver1"
   myserver1.vm.network :private_network, ip: "33.33.33.31"
   myserver1.vm.provision :ansible_local do |ansible|
     ansible.playbook = "playbook/master.yml"
   end
  end

  config.vm.define "myserver2" do |myserver2|
   myserver2.vm.hostname = "myserver2"
   myserver2.vm.network :private_network, ip: "33.33.33.32"
   myserver2.vm.provision :ansible_local do |ansible|
     ansible.playbook = "playbook/node.yml"
   end
  end

  config.vm.define "myserver3" do |myserver3|
   myserver3.vm.hostname = "myserver3"
   myserver3.vm.network :private_network, ip: "33.33.33.33"
   myserver3.vm.provision :ansible_local do |ansible|
     ansible.playbook = "playbook/node.yml"
   end
  end

end
