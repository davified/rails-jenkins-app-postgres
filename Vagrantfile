# Vagrant.configure(2) do |config|
# 	config.vm.define "jenkins" do |jenkins|
# 	 	jenkins.vm.hostname = "ubuntu.jenkins"
# 		jenkins.vm.network "private_network", ip: "192.168.0.252"
# 		jenkins.vm.hostname = "jenkins"
# 	end
# end

Vagrant.configure("2") do |config|
  config.vm.box_check_update = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.ssh.insert_key = false

  if Vagrant.has_plugin?("vagrant-dns")
    config.dns.tld = "vagrant"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "2048"
    vb.cpus = "4"
  end

  config.vm.define "jenkins" do |c|
    c.vm.box = "ubuntu/trusty64"
    c.vm.hostname = "ubuntu.jenkins"
    c.vm.network "private_network", ip: "192.168.0.252"

    c.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "infrastructure/ansible/jenkins.yml"
      # ansible.inventory_path = "infrastructure/ansible/inventory/aws"
    end
  end
end
