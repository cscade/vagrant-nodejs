# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64_vmware.box"
  
  config.vm.provision "chef_solo" do |chef|
    chef.add_recipe "nodejs"
    chef.json = {
      "nodejs" => {
        "version" => "0.10.20"
      }
    }
  end
  
end
