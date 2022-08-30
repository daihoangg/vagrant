#File mau cho ubuntu

Vagrant.configure("2") do |config|

  # boxes at https://vagrantcloud.com/search.
  # Get image ubuntu
  config.vm.box = "generic/ubuntu2004"
  
  # Set hostname
  config.vm.hostname = "ubuntu"
  
  # Create ip static and NAT
  config.vm.network "private_network", ip: "192.168.12.13"
  
  # Configuration virtualmachine
  config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #   # Customize the amount of memory on the VM:
    vb.name = "demo"
    vb.memory = "4096"
    vb.cpus = 2
  end
  
  # Run shell
  config.vm.provision "shell", inline: <<-SHELL
    apt -y update
    apt -y upgrade
    
    # change pass root = 123456
    #echo "123456" | passwd --stdin root
    #sed -i 's/^PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
    #systemctl reload sshd
    
  SHELL


  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"


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

  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
 
end
