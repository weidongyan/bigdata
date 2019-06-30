Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.network "private_network", ip: "172.25.249.11"
  config.vm.hostname = "hadoopnode"
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provision.yml"
  end
  config.vm.synced_folder ".", "/vagrant", type: "nfs"

  config.vm.provider "virtualbox" do |vb|
     vb.memory = "4096"
     vb.gui = true
     vb.cpus = 4
     vb.customize ["modifyvm", :id, "--clipboard",   "bidirectional"]
     vb.customize ["modifyvm", :id, "--draganddrop", "bidirectional"]
  end
end
