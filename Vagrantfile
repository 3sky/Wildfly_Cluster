# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "debian/stretch64"
  config.ssh.forward_agent = true
  config.vm.synced_folder "src/wild_src", "/wild_src"
  config.vm.synced_folder "src/jdk_src", "/jdk_src"
  config.vm.synced_folder "src/jre_src", "/jre_src" 
  config.vm.synced_folder "cfg", "/config"
  config.vm.network :public_network
  config.vbguest.auto_update = true

  config.vm.define "myserver1" do |myserver1|
    myserver1.vm.hostname = "myserver1"
    myserver1.vm.network :private_network, ip: "33.33.33.31"
    myserver1.vm.network "forwarded_port", guest: 8080, host: 8080
    myserver1.vm.network "forwarded_port", guest: 9990, host: 9990
    myserver1.vm.network "forwarded_port", guest: 9999, host: 9999
  end

  config.vm.define "myserver2" do |myserver2|
   myserver2.vm.hostname = "myserver2"
   myserver2.vm.network :private_network, ip: "33.33.33.32"
  end

  config.vm.define "myserver3" do |myserver3|
   myserver3.vm.hostname = "myserver3"
   myserver3.vm.network :private_network, ip: "33.33.33.33"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook/playbook.yml"
    ansible.groups = {
      "master" => ["myserver1"],
      "nodes" => ["myserver[2:3]"]
    }
  end

end
