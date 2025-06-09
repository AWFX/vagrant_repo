ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'

Vagrant.configure(2) do |config|

    N = 2
    (1..N).each do |i|
      config.vm.define "host#{i}" do |node|
        node.vm.box = "debian/bullseye64"
        node.vm.synced_folder "./data", "/vagrant"
        node.vm.hostname = "host#{i}"
        node.vm.network "private_network", ip:"10.0.26.1#{i}"
        node.vm.provider "virtualbox" do |vb|
          vb.memory = "2048"
          vb.name = "host#{i}"
          vb.cpus = 2
        end
      end
    end
end
