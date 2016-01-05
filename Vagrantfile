# -*- mode: ruby -*-
# vi: set ft=ruby :
# Vagrant file for development purposes

Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  config.vm.define "centos64", primary: true do |centos64|
    centos64.vm.box = "centos6.4"
    centos64.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.4.2/centos64-x86_64-20140116.box"    
    centos64.vm.network "forwarded_port", guest: 80, host: 8080
  end


  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.sudo  = true
    ansible.verbose = 'vv'
  end
end

