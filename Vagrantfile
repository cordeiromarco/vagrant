if Vagrant::VERSION < "2.0.0"
  $stderr.puts "Must redirect to new repository for old Vagrant versions"
  Vagrant::DEFAULT_SERVER_URL.replace('https://vagrantcloud.com')
end

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = false
#  config.vm.synced_folder "shared/", "/shared", create: true
 
  config.vm.define "centos7-devbox" do |server|
    server.vm.provider "virtualbox" do |vb|
	     vb.customize ["modifyvm", :id, "--cpus", "2"]
       vb.name = "centos7-devbox"
       vb.memory = 2048
    end
    server.vm.hostname = "centos7-devbox.university"
    server.vm.network :private_network, ip: "192.168.103.100"
  end

  #apps  
  config.vm.provision "shell", inline: "sudo su"
  config.vm.provision "shell", inline: "yum install -y kernel-devel"
  config.vm.provision "shell", inline: "yum update -y"
  config.vm.provision "shell", inline: "yum install -y epel-release"
  config.vm.provision "shell", inline: "yum update -y"
  config.vm.provision "shell", inline: "yum install -y mc htop expect ansible nano net-tools telnet git wget"
  
  #selinuxoff
  config.vm.provision "shell", inline: "sed -i 's/.*SELINUX=enforcing.*/SELINUX=disabled/' /etc/selinux/config"  
  
end
