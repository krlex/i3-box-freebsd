# -*- mode: ruby; -*-
Vagrant.configure("2") do |config|
  config.vm.box = "krlex/Freebsd-12.0.p9-Release-cbsd"
  config.vm.hostname = "vagrant"
  config.vm.network "private_network", ip: "192.168.33.20"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
  end
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provision/site.yml"
    ansible.host_key_checking = false
    ansible.raw_arguments = ["-e", "ansible_python_interpreter='/usr/bin/env python3.6'"]
    ansible.groups = {
      "vagrant" => ["default"],
    }

  end
end
