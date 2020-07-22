# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
  end

  config.vm.network :forwarded_port, guest: 5000, host: 5000

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update -y
    apt-get upgrade -y
    apt-get dist-upgrade -y
    apt-get install -y python3-dev python3-wheel python3-setuptools python3-six python3-pip
    apt-get install build-essential -y
    apt-get install -y git vim curl
    echo 'curl https://sh.rustup.rs -sSf | sh -s -- -y;' | su vagrant
   SHELL
end