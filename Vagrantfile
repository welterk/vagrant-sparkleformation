# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.provider "virtualbox" do |v|
        v.memory = 4096
    end
	
	#optional, cuz i like to map a folder in my vagrantbox
    #Create Folder and map to a Windows Folder:
    #config.vm.provision "shell", inline: "mkdir -p /d/projekte"
    #if File.directory?(File.expand_path("D:\\Projekte"))
    #    config.vm.synced_folder "D:\\Projekte", "/d/projekte"
    #end
	
	config.vm.provision "shell", inline: <<-SHELL
    # Update and upgrade the server packages.
    sudo apt-get -y upgrade
	# Use Repo brightbox/ruby-ng
	sudo apt-add-repository ppa:brightbox/ruby-ng
	sudo apt-get update
	sudo apt-get install -y ruby2.4
	sudo apt-get install -y ruby2.4-dev
	sudo apt-get install -y build-essential
	sudo gem install bundler
	sudo gem install sfn
  SHELL
end