# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define "controller" do |controller|
    controller.vm.box = "ubuntu/trusty64"
    controller.vm.hostname = "controller"
    controller.vm.network "private_network", ip: "192.168.81.10"
    #controller.vm.provision :ansible do |ansible|
        #Disable default limit to connect to all the machines
    #   ansible.limit = "all"
    #   ansible.playbook = "controller.yml"
     #end
  end

  config.vm.define "web" do |web|
    web.vm.box="nrel/CentOS-6.5-x86_64"
    web.vm.hostname = "web"
    web.vm.network "private_network", ip: "192.168.81.20"
    web.vm.network "forwarded_port", guest: 80, host: 8080
  end

  config.vm.define "db" do |db|
    db.vm.box = "nrel/CentOS-6.5-x86_64"
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.81.30"
  end

end
