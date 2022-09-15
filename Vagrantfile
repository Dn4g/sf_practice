# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |django_config|
  # Every Vagrant virtual environment requires a box to build off of.
  django_config.vm.box = "bionic64"
  django_config.vm.provision "shell", inline: <<-SHELL
  
django_config.vm.box_url = "https://cloud-images.ubuntu.com/bionic/current/bionic-server-cloudimg-amd64-vagrant.box"
  

django_config.vm.provider :virtualbox do |p|
    p.customize ["modifyvm", :id, "--memory", 2048]
    p.customize ["modifyvm", :id, "--cpus", 2]
    p.customize ["modifyvm", :id, "--cpuexecutioncap", 50]
  end

  # Configure a synced folder between HOST and GUEST
  django_config.vm.synced_folder ".", "/vagrant", id: "vagrant-root", :mount_options => ["dmode=777","fmode=777"]
# Install git for version control, pip for install python packages
echo 'Installing git, Python 3, and pip...'
apt install python3 psycopg2
curl -s https://bootstrap.pypa.io/get-pip.py | python3.4 
pip3 install django


SHELL
end
