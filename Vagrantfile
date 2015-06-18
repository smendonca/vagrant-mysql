# -*- mode: ruby -*-
# # vi: set ft=ruby :

VAGRANTFILE_API_VERSION = '2'
VAGRANT_IP = '172.16.8.9'
VAGRANT_NAME = 'vagrant-mysql'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box      = 'ubuntu/trusty64'
  config.vm.hostname = VAGRANT_NAME

  config.vm.network 'private_network', ip: VAGRANT_IP

  config.vm.define VAGRANT_NAME

  config.vm.provider :virtualbox do |vb|
    vb.customize ['modifyvm', :id, '--ostype', 'Debian_64']
    vb.customize ['modifyvm', :id, '--memory', 2048]
    vb.customize ['modifyvm', :id, '--chipset', 'ich9']
    vb.customize ['modifyvm', :id, '--vram', '10']
    vb.customize ['modifyvm', :id, '--ioapic', 'on']
    vb.customize ['modifyvm', :id, '--cpus', 2]
    vb.name = VAGRANT_NAME
  end

  config.vm.provision 'shell', path: 'bootstrap'
end
