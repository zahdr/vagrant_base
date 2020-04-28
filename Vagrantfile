BOX_IMAGE = "hashicorp/bionic64"
NODE_COUNT = 3

Vagrant.configure("2") do |config|
  config.vm.box = BOX_IMAGE
  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end

  (1..NODE_COUNT).each do |i|
    config.vm.define "v#{i}" do |node|
      node.vm.hostname = "v#{i}"
      node.vm.network "private_network", ip: "172.20.20.#{i + 10}"
    end
  end

  # provision on all nodes
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "/home/vagrant/.ssh/authorized_keys"
end
