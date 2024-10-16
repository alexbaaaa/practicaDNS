# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Configuración de la máquina "venus"
  config.vm.define "venus" do |venus|
    venus.vm.box = "debian/bullseye64"
    venus.vm.hostname = "venus"
    venus.vm.network "private_network", ip: "192.168.57.102"
  end

  # Configuración de la máquina "tierra"
  config.vm.define "tierra" do |tierra|
    tierra.vm.box = "debian/bullseye64"
    tierra.vm.hostname = "tierra"
    tierra.vm.network "private_network", ip: "192.168.57.103"
  end

end
