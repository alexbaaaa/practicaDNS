# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Configuracion carpetas compartidas
  config.vm.synced_folder "./config_file", "/vagrant_config_file"
  # Configuración de la máquina "venus"
  config.vm.define "venus" do |venus|
    venus.vm.box = "debian/bullseye64"
    venus.vm.hostname = "venus.sistema.test"
    venus.vm.network "private_network", ip: "192.168.57.102"

    # Provision de la maquina Venus 
    venus.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get upgrade -y
      apt-get install -y bind9 dnsutils
      # Copiado de archivo esterno de configuracion
      cp /vagrant_config_file/named.conf.options /etc/bind/
      systemctl restart bind9
    SHELL
  end

  # Configuración de la máquina "tierra"
  config.vm.define "tierra" do |tierra|
    tierra.vm.box = "debian/bullseye64"
    tierra.vm.hostname = "tierra.sistema.test"
    tierra.vm.network "private_network", ip: "192.168.57.103"

    # Provision de la maquina tierra 
    tierra.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get upgrade -y
      apt-get install -y bind9 dnsutils
      # Copiado de archivo esterno de configuracion
      cp /vagrant_config_file/named.conf.options /etc/bind/
      systemctl restart bind9
    SHELL
  end

end
