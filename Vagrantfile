#ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'

Vagrant.configure(2) do |config|

  #first machine
  config.vm.define "web" do |web|
    web.vm.box = "debian/bullseye64"
    #web.vm.synced_folder "./data", "/ho"
    web.vm.hostname = "web"
    web.vm.provision "shell",
      inline: 'echo "ITS ARTYOM" >> /home/vagrant/main.txt'
    web.vm.provider "virtualbox" do |vb|
      vb.name = "debian_web"
      vb.cpus = 1
      vb.memory = 1024
    end
  end

  #second machine
  config.vm.define "db" do |db|
    db.vm.box = "almalinux/9"
    db.vm.hostname = "artyom"
    db.vm.synced_folder "./data", "/vagrant"
    db.vm.provision "shell",
      inline: "dnf update -y && dnf install mariadb -y"
    db.vm.provider "virtualbox" do |vb|
      vb.name = "database"
      vb.cpus = 2
      vb.memory = 2048
    end
  end

  #kali machine
  config.vm.define "kali" do |kali|
    kali.vm.synced_folder "data/", "/vagrant"
    #kali.vm.hostname = "kali"
    kali.vm.box = "kalilinux/rolling"
    kali.vm.provider "virtualbox" do |vb|
      vb.cpus = 4
      vb.memory = 4096
      vb.name = "kali"
      vb.gui = false
    end
  end
end
