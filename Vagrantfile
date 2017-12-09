# -*- mode: ruby -*-
# vi: set ft=ruby :


require 'yaml'
Vagrant.require_version '>=1.8.6'

Vagrant.configure(2) do |config|
  _config = YAML::load(
    File.open(
      File.join(File.dirname(__FILE__), 'setup.yml'),
      File::RDONLY
      ).read
    )

  # Machine Settings
  config.vm.box = _config['box']
  config.vm.box_version = "> 0"
  config.vm.box_check_update = true

  config.vm.hostname = _config['hostname']
  config.vm.network :private_network, ip: _config['ip']

config.vm.synced_folder _config['synced_folder'],
  _config['document_root'], :create => "true", :mount_options => ['dmode=755', 'fmode=644']


config.vm.provision :ansible_local do |ansible|
  ansible.playbook = "provision/playbook.yml"
end


end
