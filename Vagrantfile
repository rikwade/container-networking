# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.10"

  config.vm.provider :virtualbox do |v|
    v.name = "container-networking"
    v.memory = "1024"
    v.cpus = 1
    v.gui = false
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.hostname = "ubuntu"
  #config.vm.network :private_network, ip: "172.16.9.99"
  config.vm.network "forwarded_port", guest: 22, host: 2222, auto_correct: true
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
  config.vm.network "forwarded_port", guest: 30001, host: 8081, auto_correct: true
  config.vm.network "forwarded_port", guest: 8080, host: 8888, auto_correct: true

  config.vm.synced_folder "sync/", "/home/vagrant/sync", create: true, disabled: false

  #config.vm.provision :shell, path: "provision.sh"
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
    ansible.extra_vars = {
        ansible_python_interpreter: "/usr/bin/python3", 
    }
  end
end
