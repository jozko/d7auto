# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "devzero.si"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.56.12"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    # Display VirtualBox GUI when booting the machine
    vb.gui = false
 
    # Customize the amount of memory on the VM:
    vb.memory = "1024"
    vb.customize ["modifyvm", :id, "--cpus", "2"]
    vb.customize ["modifyvm", :id, "--cpuexecutioncap", "75"]
  end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
    mkdir -p /home/ubuntu/.ssh
    chown ubuntu:ubuntu /home/ubuntu/.ssh
    chmod 700 /home/ubuntu/.ssh
    echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC880XbBihLwtfz61xJR0WcabV+DMrBivjjIpmhfU1uJQOR/2dRlw6G9fiDiunNaENHtOD02NMz+FElZiGZKKnBjlVqY7Dul6zzalR5h/irEqpb9LVj1JJswfBzWyuSwCU6ZnMM1MYr+WLfr5MW+MwJRUWswEmSbLB7RaTmBjlQLqaQYMT0fLJUVIMjLtPTnb8dII2NXArh3Yh/95egnmjKbKvB+CM0SzzazzbGaQOe326+4c9a63Woqny5WkaibHgYVkiQLwCzZbF8MNxsh7Xfx4KT+8MwIGa9DBiFM5Y82E9TeDPKlSgO5af+puwiMEBLq1w6HXnsZY8aHXUaDEwb jozko@zomg.si" >> /home/ubuntu/.ssh/authorized_keys
    chmod 600 /home/ubuntu/.ssh/authorized_keys
    apt-get update
    apt-get -y dist-upgrade
    apt-get -y install python
    reboot
  SHELL
end
