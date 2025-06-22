ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'

Vagrant.configure(2) do |config|

  NAMEING = ['suricata', 'nmap']
  ADDR = ['10.0.26.11/24', '10.0.26.12/24']

  N = 2
  (1..N).each do |i|
    config.vm.define "host#{i}" do |node|
      node.vm.box = "debian/bullseye64"
      node.vm.synced_folder "./data", "/vagrant"
      node.vm.hostname = NAMEING[i - 1]
      node.vm.network "private_network", ip: ADDR[i - 1]
      node.vm.provider "virtualbox" do |vb|
        vb.memory = "3072"
        vb.name = NAMEING[i - 1]
        vb.cpus = 3
  N = 2
  (1..N).each do |i|
    config.vm.define "host#{i}" do |node|
      node.vm.box = "debian/bullseye64"
      node.vm.synced_folder "./data", "/vagrant"
      node.vm.hostname = NAMEING[i - 1]
      node.vm.network "private_network", ip: ADDR[i - 1]
      node.vm.provider "virtualbox" do |vb|
        vb.memory = "3072"
        vb.name = NAMEING[i - 1]
        vb.cpus = 3
      end
    end
  end

end

  end

end

