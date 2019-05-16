# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.define  "awscli" do |host|
    host.vm.box = "ubuntu/xenial64"
    host.vm.hostname = "awscli"
    host.vm.network "private_network", ip: "192.168.50.92"
    # ---- boostrap install script ----
    host.vm.provision "shell", path: "./config/strap_aws", privileged: false
    # ---- direnv, sourcing utility ----
    host.vm.provision "shell", path: "./config/direnv-setup", privileged: false
    # ---- copy terraform .tf files ----
    host.vm.provision "file", source: "./terraform_files/main.tf", destination: "$HOME/terransible/"
    host.vm.provision "file", source: "./terraform_files/variables.tf", destination: "$HOME/terransible/"
    host.vm.provision "file", source: "./terraform_files/terraform.tfvars", destination: "$HOME/terransible/"
  end
end
