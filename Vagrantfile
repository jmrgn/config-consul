# -*- mode: ruby -*-
# vi: set ft=ruby :
$script = <<SCRIPT

echo Installing dependencies...
sudo apt-get install -y unzip curl

echo Fetching Consul...
cd /tmp/
wget https://dl.bintray.com/mitchellh/consul/0.4.1_linux_amd64.zip -O consul.zip

echo Installing Consul...
unzip consul.zip
sudo chmod +x consul
sudo mv consul /usr/bin/consul

SCRIPT

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  # Disable automatic box update checking. If you disable this, then
  
  config.vm.define "consul1" do |consul1|
    consul1.vm.provision "shell", inline: $script
    consul1.vm.box = "hashicorp/precise64"
    consul1.vm.hostname = "consul1"
    consul1.vm.network "private_network", ip: "172.20.20.91"
    # consul1.vm.network "forwarded_port", guest: 8081, host: 8081
  end
end
