# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"

  config.vm.network "forwarded_port", guest:  25, host: 1025 # SMTP
  config.vm.network "forwarded_port", guest: 143, host: 1143 # IMAP

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.compatibility_mode = "2.0"
    ansible.become = true
    ansible.extra_vars = {
      mail_domains: ["example.com"],
      mail_users: [{
        username: "mail-a@example.com",
        password: "swordfish-a"
      }, {
        username: "mail-b@example.com",
        password: "swordfish-b"
      }],
      mail_aliases: [
        { source: 'alias-a@example.com', destination: 'mail-a@example.com' },
        { source: 'alias-b@example.com', destination: 'mail-b@example.com' }
      ]
    }
  end
end
