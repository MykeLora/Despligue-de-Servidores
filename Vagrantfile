Vagrant.configure("2") do |config|
    config.vm.define "web1" do |web1|
      web1.vm.box = "ubuntu/focal64"
      web1.vm.network "private_network", ip: "192.168.33.10"
      web1.vm.synced_folder "./html", "/var/www/html"
      web1.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache2
        systemctl enable apache2
        systemctl start apache2
      SHELL
      web1.vm.boot_timeout = 600  # Aumenta el tiempo de espera a 600 segundos
    end
  
    config.vm.define "web2" do |web2|
      web2.vm.box = "ubuntu/focal64"
      web2.vm.network "private_network", ip: "192.168.33.11"
      web2.vm.synced_folder "./html", "/var/www/html"
      web2.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache2
        systemctl enable apache2
        systemctl start apache2
      SHELL
      web2.vm.boot_timeout = 600  # Aumenta el tiempo de espera a 600 segundos
    end
  end
  