Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |v|
      v.name = "VAGRANT-ZABBIX-AGENT"
      v.memory = "1024"
      v.cpus = "1"
  end
  
    config.vm.box = "ubuntu/focal64"
    config.vm.network "public_network", ip: "192.168.10.110", bridge:"Intel(R) Wireless-AC 9560"
    config.vm.synced_folder "./ansible" , "/ansible"
  
    
  
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y ansible
      ansible-playbook --connection=local /ansible/playbook.yml
      
    SHELL
  end