# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "debian/jessie64"

  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
  config.vm.network "forwarded_port", guest: 3306, host: 3307, auto_correct: true

  config.vm.synced_folder "../", "/var/www/default", create: true, group: "www-data", owner: "www-data"

  config.vbguest.auto_update = false
  config.vbguest.no_remote = true

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "lemp.yml"
  end

end
