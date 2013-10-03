# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64_vmware.box"
  
  config.vm.hostname = "node-dev"
  
  config.vm.provision "chef_solo" do |chef|
    chef.add_recipe "redisio::install"
    chef.add_recipe "redisio::enable"
    chef.add_recipe "nodejs"
    chef.add_recipe "couchdb::source"
    
    chef.json = {
      "couch_db" => {
        "src_version" => "1.4.0",
        "src_mirror" => "http://mirrors.ibiblio.org/apache/couchdb/source/1.4.0/apache-couchdb-1.4.0.tar.gz"
      },
      "nodejs" => {
        "version" => "0.10.20"
      },
      "redis" => {
        "version" => "2.6.16"
      }
    }
  end
  
end
