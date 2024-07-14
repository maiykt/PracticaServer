# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    # Configuración de la primera máquina virtual
    config.vm.define "web1" do |web1|
      web1.vm.box = "ubuntu/bionic64"
      web1.vm.network "private_network", ip: "192.168.33.10"
      web1.vm.hostname = "web1"
  
      # Provisión de la máquina para instalar Apache y configurar la carpeta compartida
      web1.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
        sudo systemctl enable apache2
      SHELL
  
      web1.vm.synced_folder "./html", "/var/www/html"
    end
  
    # Configuración de la segunda máquina virtual
    config.vm.define "web2" do |web2|
      web2.vm.box = "ubuntu/bionic64"
      web2.vm.network "private_network", ip: "192.168.33.11"
      web2.vm.hostname = "web2"
  
      # Provisión de la máquina para instalar Apache y configurar la carpeta compartida
      web2.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
        sudo systemctl enable apache2
      SHELL
  
      web2.vm.synced_folder "./html", "/var/www/html"
    end
  end
  