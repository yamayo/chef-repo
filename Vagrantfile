# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos_65"

  config.vm.network :private_network, ip: "192.168.33.10"

  config.ssh.forward_agent = true

  config.omnibus.chef_version = :latest

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks", "site-cookbooks"]

    chef.json = {
      run_list: [
        "yum::exclude_kernel",
        "rbenv",
        "rbenv::ruby_build"
      ]
    }

  end

end
