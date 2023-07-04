Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    config.vm.network "public_network", bridge: "Intel(R) Wireless-AC 9560"   # Modo bridge
    
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y mysql-server
      systemctl start mysql
  
      wget https://repo.zabbix.com/zabbix/5.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_5.4-1+bionic_all.deb
      dpkg -i zabbix-release_5.4-1+bionic_all.deb
      apt-get update
      apt-get install -y zabbix-server-mysql
    SHELL
  end
  
  

