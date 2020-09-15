# Vagrant-Related
This repo mainly contains Vagrant test and learning stuffs. Please refer to the Wiki tab.

To configure Vagrant with NAT and Host-only network
$ cat Vagrantfile
Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "echo Hello"

  config.vm.define "master" do |master|
    master.vm.network "private_network", ip: "192.168.50.4",
    vitualbox__intnet: true
    master.vm.box = "centos/7"
  end

  config.vm.define "host1" do |host1|
    host1.vm.network "private_network", ip: "192.168.50.5",
    vitualbox__intnet: true
    host1.vm.box = "centos/7"
  end
end

