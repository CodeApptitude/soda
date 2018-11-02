# -*- mode: ruby -*-
# vi: set ft=ruby :


require 'yaml'
#Vagrant.require_version '>=2.2.0'

Vagrant.configure(2) do |config|
  config.vm.box = "codeapptitude/soda"
  
  config.vm.box_check_update = false

  config.vm.hostname = "192.168.33.13"
  config.vm.network "private_network", ip: "sodabox"
  config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

end
