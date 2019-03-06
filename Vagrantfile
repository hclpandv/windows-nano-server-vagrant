# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  #--------------------------------------------------------
  #------ Creating VM: a webserver for the devops-challenge
  #--------------------------------------------------------
  config.vm.define "nanoserver" do |nano|
    nano.vm.box = "mwrock/WindowsNano"
    nano.vm.hostname = 'windows-nano-server'
    # Assigning IP, as per guidelines in devops-challenge:
    nano.vm.network "private_network", ip: "10.10.10.30"
    #------ Using Virtualbox provider for the exercise
    nano.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.customize ["modifyvm", :id, "--name", "windows-nano-server"]  
      # Customize the amount of memory on the VM:
      vb.memory = "1024"
      # Use the max number of CPU, as per guidelines in devops-challenge:
      cpus = `nproc`.to_i
      vb.customize ["modifyvm", :id, "--cpus", cpus]
    end
  end
end
