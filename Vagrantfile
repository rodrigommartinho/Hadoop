Vagrant.configure(2) do |config|
  config.ssh.insert_key = false 
  config.vm.define "hadoop" do |hadoop|
    hadoop.vm.box = "geerlingguy/centos7"
    hadoop.vm.box_version = "1.2.3"
    hadoop.vm.network "private_network", ip: "192.168.199.8"
    hadoop.vm.hostname = "hadoop.example.com"
    hadoop.vm.provision "shell", path: "scripts/install_ambari_server.sh"
    hadoop.vm.network "forwarded_port", guest: 8080, host: 8080
    hadoop.vm.provider "virtualbox" do |v|
      v.memory = 12288
      v.cpus = 2
      v.customize ['modifyvm', :id, '--cableconnected1', 'on']
    end
  end
end
