# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.require_version ">= 1.6.2"

Vagrant.configure("2") do |config|

    config.vm.define "vagrant-windows-2019" do |cfg|
        cfg.vm.box = "windows2019"
        cfg.vm.communicator = "winrm"
        cfg.winrm.username = "vagrant"
        cfg.winrm.password = "vagrant"
        cfg.vm.guest = :windows
        cfg.windows.halt_timeout = 15
        # cfg.vm.network :forwarded_port, guest: 3389, host: 3389, id: "rdp", auto_correct: true, "private_network", ip: "192.168.56.10"
        cfg.vm.network "private_network", ip: "192.168.56.10"

    config.vm.define "linux-worker1" do |cfg|
        cfg.vm.box      = "generic/ubuntu2004"
        cfg.vm.hostname = "ubuntu"
        cfg.vm.network  "private_network", ip: "192.168.50.11"

        
    config.vm.provider :virtualbox do |v, override|
        v.gui = true
        v.customize ["modifyvm", :id, "--memory", 2048]
        v.customize ["modifyvm", :id, "--cpus", 2]
        v.customize ["modifyvm", :id, "--vram", 128]
        v.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
        v.customize ["setextradata", "global", "GUI/SuppressMessages", "all" ]
    end
end
