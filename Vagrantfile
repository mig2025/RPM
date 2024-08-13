# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.define "fedora" do |server|
    server.vm.box = "fedora/39"
    server.vm.hostname = "repo-server"
    server.vm.network "forwarded_port", guest: 80, host: 8080
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
    server.vm.provision "ansible" do |ansible|
       ansible.verbose = "v"
       ansible.playbook = "haupt.yml"
   end
  end
end