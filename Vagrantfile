VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "saucy64"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/saucy/current/saucy-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.network :forwarded_port, guest: 8888, host: 8888
  config.vm.network :forwarded_port, guest: 8000, host: 8000
  config.vm.network :private_network, ip: "192.168.33.10"
  #config.vm.provision :docker 

  config.vm.provision :shell, :inline => <<-EOT
    apt-get install -y curl git vim
    apt-get install -y python-numpy python-scipy ipython-notebook 
    apt-get install -y python-matplotlib
    apt-get install -y python-sympy
    apt-get install -y python-pip
    pip install pydy
    pip install --upgrade sympy
    #mkdir /var/notebooks
  EOT

  #config.vm.synced_folder "pydy-tutorial-pycon-2014/notebooks", "/var/notebooks"
end
