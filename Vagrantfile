# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|
config.hostmanager.enabled = true
config.hostmanager.ignore_private_ip = false 
config.hostmanager.include_offline = true

  config.vm.define "a", primary: true do |a|
    a.vm.box = "ubuntu/trusty64"
	a.vm.hostname = "a.example.com"
	a.vm.network "private_network", ip: "192.168.33.10"
	a.hostmanager.aliases = %w(a)
#a.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh"

end

  config.vm.define "b" do |b|
      b.vm.box = "ubuntu/precise64"
	  b.vm.hostname ="b.example.com"
	  b.vm.network "private_network", ip: "192.168.33.20"
	  b.hostmanager.aliases = %w(b)
	#  web.vm.network "forwarded_port", guest:80, host:8080
	#b.vm.network :forwarded_port, guest: 22, host: 10222, id: "ssh"
	
end
     
	 config.vm.define "c" do |c|
       c.vm.box= "ubuntu/trusty64"
       c.vm.hostname ="c.example.com"
       c.vm.network "private_network", ip: "192.168.33.30"
	   c.hostmanager.aliases = %w(c)
	 #  c.vm.network :forwarded_port, guest: 22, host: 10322, id: "ssh"
	 
 end
      
	  
    #config.vm.define "d" do |d|
     #  d.vm.box= "ubuntu/precise64"
      # d.vm.hostname ="d"
       #d.vm.network "private_network", ip: "192.168.33.40" 
	 #  d.vm.network :forwarded_port, guest: 22, host: 10422, id: "ssh"
#end
 config.vm.provision "shell", inline: <<-SHELL
  sudo apt-get update
  sudo apt-get install -y docker.io
    SHELL
end