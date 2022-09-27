# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # p1jenkins server
  config.vm.define "p1jenkins-pipeline" do |p1jenkins|
    p1jenkins.vm.box = "debian/buster64"
    p1jenkins.vm.hostname = "p1jenkins-pipeline"
    p1jenkins.vm.box_url = "debian/buster64"
    p1jenkins.vm.network :private_network, ip: "192.168.1.5"
    p1jenkins.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "p1jenkins-pipeline"]
      v.customize ["modifyvm", :id, "--cpus", "2"]
    end
    config.vm.provision "shell", inline: <<-SHELL
      sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config    
      service ssh restart
    SHELL
    p1jenkins.vm.provision "shell", path: "install_p1jenkins.sh"
  end
  # # serveur dev
  # config.vm.define "srvdev-pipeline" do |srvdev|
  #   srvdev.vm.box = "debian/buster64"
  #   srvdev.vm.hostname = "srvdev-pipeline"
  #   srvdev.vm.box_url = "debian/buster64"
  #   srvdev.vm.network :private_network, ip: "192.168.5.3"
  #   srvdev.vm.provider :virtualbox do |v|
  #     v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  #     v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  #     v.customize ["modifyvm", :id, "--memory", 512]
  #     v.customize ["modifyvm", :id, "--name", "server_dev"]
  #     v.customize ["modifyvm", :id, "--cpus", "1"]
  #   end
  #   config.vm.provision "shell", inline: <<-SHELL
  #     sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config    
  #     service ssh restart
  #   SHELL
  # end
  #   # serveur stage/recette
  # config.vm.define "srvstage-pipeline" do |srvstage|
  #   srvstage.vm.box = "debian/buster64"
  #   srvstage.vm.hostname = "srvstage"
  #   srvstage.vm.box_url = "debian/buster64"
  #   srvstage.vm.network :private_network, ip: "192.168.5.7"
  #   srvstage.vm.provider :virtualbox do |v|
  #     v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  #     v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  #     v.customize ["modifyvm", :id, "--memory", 512]
  #     v.customize ["modifyvm", :id, "--name", "server_stage"]
  #     v.customize ["modifyvm", :id, "--cpus", "1"]
  #   end
  #   config.vm.provision "shell", inline: <<-SHELL
  #     sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config    
  #     service ssh restart
  #   SHELL
  # end
   # serveur prod
  #  config.vm.define "srvprod-pipeline" do |srvprod|
  #   srvprod.vm.box = "debian/buster64"
  #   srvprod.vm.hostname = "srvprod"
  #   srvprod.vm.box_url = "debian/buster64"
  #   srvprod.vm.network :private_network, ip: "192.168.5.4"
  #   srvprod.vm.provider :virtualbox do |v|
  #     v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  #     v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  #     v.customize ["modifyvm", :id, "--memory", 512]
  #     v.customize ["modifyvm", :id, "--name", "server_prod"]
  #     v.customize ["modifyvm", :id, "--cpus", "1"]
  #   end
  #   config.vm.provision "shell", inline: <<-SHELL
  #     sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config    
  #     service ssh restart
  #   SHELL
  # end
  #  # serveur bd_postgres
  #  config.vm.define "srvbdd-pipeline" do |srvbdd|
  #   srvbdd.vm.box = "debian/buster64"
  #   srvbdd.vm.hostname = "srvbdd"
  #   srvbdd.vm.box_url = "debian/buster64"
  #   srvbdd.vm.network :private_network, ip: "192.168.5.6"
  #   srvbdd.vm.provider :virtualbox do |v|
  #     v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  #     v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  #     v.customize ["modifyvm", :id, "--memory", 512]
  #     v.customize ["modifyvm", :id, "--name", "server_bdd"]
  #     v.customize ["modifyvm", :id, "--cpus", "1"]
  #   end
  #   config.vm.provision "shell", inline: <<-SHELL
  #     sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config    
  #     service ssh restart
  #   SHELL
  #   srvbdd.vm.provision "shell", path: "install_srvpostgres.sh"
  # end
end




