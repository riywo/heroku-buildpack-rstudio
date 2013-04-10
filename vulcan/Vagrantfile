# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "lucid64"
  config.vm.box_url = "http://files.vagrantup.com/lucid64.box"
  config.vm.network :private_network, ip: "192.168.39.10"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    vb.customize ["modifyvm", :id, "--cpus", 4]
  end

  config.vm.provision :shell, :inline => "apt-get install curl build-essential bzip2 -y"
  config.vm.provision :shell, :path => "build-rstudio", :args => "0.97.336"
end
