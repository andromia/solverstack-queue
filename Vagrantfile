# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "bento/ubuntu-16.04"
  
  config.vm.network :forwarded_port, guest: 7878, host: 7878

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update -y
    apt-get upgrade -y
    apt-get dist-upgrade -y
    apt-get install build-essential -y
    apt-get install -y git vim curl
    echo 'curl https://sh.rustup.rs -sSf | sh -s -- -y;' | su vagrant
   SHELL
end