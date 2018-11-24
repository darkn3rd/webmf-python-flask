# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 5000, host: 5000

  config.vm.provision "docker" do |docker|
    docker.build_image "/vagrant", args: "-t vagrant/flask-web"
    docker.run "vagrant/flask-web" , args: "-p 5000:5000"
  end
end
