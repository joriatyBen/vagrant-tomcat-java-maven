# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "tomcat-vm"
  end

  config.vm.network :forwarded_port, guest: 8080, host: 4000, host_ip: "127.0.0.1"
  config.vm.network "private_network", ip: "192.168.33.111"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    # Install Ansible
    apt -y install software-properties-common
    apt-add-repository --yes --update ppa:ansible/ansible
    apt update
    apt -y install ansible
    # Install Maven
    apt install -y maven
  SHELL
    
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "/home/ben/MayDay/sts_project/provisioning/tomcat-ansible/tomcat-setup.yml"
    ansible.verbose = true
  end

end
