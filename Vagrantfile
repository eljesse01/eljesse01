
Vagrant.configure("2") do |config|
 
  config.vm.box = "bento/ubuntu-18.04"
  config.ssh.username="el-jesse"
  config.ssh.password="Password"

 
  config.vm.provider "virtualbox" do |vb|
    
    vb.gui = false  
    
    vb.memory = "1024"
    vb.cpus = "1"
  end

  config.vm.define "web" do |web|
    web.vm.hostname = "Web"
    web.vm.network "private_network", ip: "192.168.2.130"
    web.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "configure.yml"
    end
  end
  

  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y wget 
  #  SHELL
end
