# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network :private_network, ip: "10.0.0.210"
    config.ssh.forward_agent = true
    config.vm.provider :virtualbox do |p|
        p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        p.customize ["modifyvm", :id, "--memory", 2048]
        p.customize ["modifyvm", :id, "--name", "docker"]
        p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        p.cpus = 2
        p.gui = true
    end

    config.vm.provision "shell",
        inline: "
          sudo apt-get --yes install software-properties-common;
          sudo apt-get --yes install python-pip;
          if ! type ansible-playbook; then
              sudo apt-add-repository --yes ppa:ansible/ansible;
              sudo apt-get --yes update ;
              sudo apt-get --yes install ansible;
          fi
          cp -R /vagrant ~/;
          chmod -x ~/vagrant/hosts;
          chmod -x ~/vagrant/provision.yml;
          cd ~/vagrant;
          ansible-playbook -i hosts provision.yml;
          "
end
