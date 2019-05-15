# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.define  "awscli" do |host|
    host.vm.box = "ubuntu/xenial64"
    host.vm.hostname = "awscli"
    host.vm.network "private_network", ip: "192.168.50.92"
    host.vm.provision "shell", path: "./config/strap_aws", privileged: false
    host.vm.provision "shell", path: "./config/direnv-setup", privileged: false
    host.vm.provision "shell", path: "./config/terraform-foundation", privileged: false
  end
end
