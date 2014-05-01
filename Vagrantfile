# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.hostname = "centos6build.local"
  config.vm.box = "centos6build"

  # Modify this to whichever box file you want to use as your build host
  config.vm.box_url = "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.5-x86_64-v20140311.box"

  config.vm.provision "shell", path: "scripts/build_python"
end
