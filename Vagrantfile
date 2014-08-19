VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  names = ["master1", "master2", "master3", "slave1", "slave2"]
  ips = ["192.168.33.11", "192.168.33.12", "192.168.33.13", "192.168.33.14", "192.168.33.15"]
  names.zip ips.each do |name, ip|
    config.vm.define name do |master|
      master.vm.network "private_network", ip: ip
    end
  end
end
