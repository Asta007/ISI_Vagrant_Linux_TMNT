Vagrant.configure("2") do |config|

  config.vm.define "Linux-TMNT" do |tmnt|
    tmnt.vm.box = "bento/ubuntu-22.04"
    tmnt.vm.box_check_update = false
    
    tmnt.vm.network "forwarded_port", guest: 3306, host: 3306
    tmnt.vm.network "private_network", ip: "192.168.33.3"
    
    tmnt.vm.synced_folder "./web", "/var/www/html"

    tmnt.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.cpus = 1
      vb.name = "Tmnt-Linux"
      vb.memory = 1024
    end

    tmnt.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y nginx
      #rm -rf /var/www/html/*
      #cp -r /vagrant/web/* /var/www/html/
      systemctl restart nginx
      
      apt-get update
      apt-get install -y mysql-server

      # Configurer MySQL pour écouter sur toutes les interfaces
      sed -i 's/bind-address.*/bind-address = 0.0.0.0/' /etc/mysql/mysql.conf.d/mysqld.cnf

      mysql -u root -e "CREATE USER 'iamroot' IDENTIFIED BY 'root123';"
      mysql -u root -e "GRANT ALL PRIVILEGES ON *.* TO 'iamroot' WITH GRANT OPTION;"
      mysql -u root -e "FLUSH PRIVILEGES;"

      systemctl restart mysql
    SHELL

  end
end