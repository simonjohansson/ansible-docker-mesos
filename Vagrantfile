VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  ["master1", "master2", "master3"].zip ["192.168.33.11", "192.168.33.12", "192.168.33.13"].each do |name, ip|
    config.vm.define name do |master|
      master.vm.network "private_network", ip: ip
    end
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "/home/simon/ansible/site.yml"
    ansible.inventory_path = "/home/simon/ansible/hosts"
    ansible.limit = "all"
  end
end
