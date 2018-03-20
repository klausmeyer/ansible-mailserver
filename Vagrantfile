# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"

  config.vm.network "forwarded_port", guest: 25, host: 1025

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.compatibility_mode = "2.0"
    ansible.become = true
  end
end
