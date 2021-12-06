Vagrant.configure("2") do |config|
 
    config.vm.box = "bento/centos-7"
    config.vm.synced_folder ".", "/vagrant"
    # config.ssh.username="el-jesse"
    # config.ssh.password="Password"

 
    config.vm.provider "virtualbox" do |vb|
      
      vb.gui = false  
      vb.memory = "512"
      vb.cpus = "1"
    end

    config.vm.define "nginx" do |nginx|
      nginx.vm.hostname = "nginx"
      nginx.vm.network "private_network", ip: "192.168.2.141"
      nginx.vm.boot_timeout = 300
      nginx.vm.provision "ansible_local" do |ansible|
          ansible.playbook = "nginxplaybook.yml"
        end
      
    end

    # config.vm.define "app2" do |app2|
    #   app2.vm.hostname = "app2"
    #   app2.vm.network "private_network", ip: "192.168.2.131"
    #   app2.vm.boot_timeout = 300
    # end

    # config.vm.define "db" do |db|
    #   db.vm.hostname = "db"
    #   db.vm.network "private_network", ip: "192.168.2.132"
    #   db.vm.boot_timeout = 300
    #   db.vm.provision "ansible_local" do |ansible|
    #      ansible.playbook = "db.yml"
    #    end
    # end

    # config.vm.define "control" do |control|
    #   control.vm.hostname = "control"
    #   control.vm.network "private_network", ip: "192.168.2.133"
    #   control.vm.boot_timeout = 300
    #   control.vm.synced_folder ".", "/vagrant"
    #   control.vm.provision "ansible_local" do |ansible|
    #     ansible.playbook = "configure.yml"
    #   end
    # end
  

  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y wget 
  #  SHELL
end
