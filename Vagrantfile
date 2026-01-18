Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "sudo apt install vim -y"
  #cinfig.vm.provision "shell",
  #config.vm.provision "shell", path: "teste.sh"

  config.vm.define "controle" do |controle|
    controle.vm.box = "shekeriev/debian-12"
    controle.vm.network "private_network", ip: "172.17.177.100"
    controle.vm.hostname = "controle"
    controle.vm.provision "shell", inline: "apt update -y && sudo apt -y full-upgrade -y"
    controle.vm.provider "virtualbox" do |vb|
      #vb.paravirtprovider = "kvm"
      vb.name = "controle"
      vb.memory = "2048"
      vb.cpus = 2
    end
  end

  config.vm.define "web" do |web|
    web.vm.box = "shekeriev/debian-12"
    web.vm.network "private_network", ip: "172.17.177.101"
    web.vm.hostname = "web"
    web.vm.provider "virtualbox" do |vb|
      #vb.paravirtprovider = "kvm"
      vb.name = "web"
      vb.memory = "512"
      vb.cpus = 2
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "shekeriev/debian-12"
    db.vm.network "private_network", ip: "172.17.177.102"
    db.vm.hostname = "db"
    db.vm.provider "virtualbox" do |vb|
      #vb.paravirtprovider = "kvm"
      vb.name = "db"
      vb.memory = "512"
      vb.cpus = 2
    end
  end
end
