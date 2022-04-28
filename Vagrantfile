Vagrant.configure("2") do |config|

  config.vm.provider :virtualbox do |v|
    v.memory = 512
  end

  config.vm.define "suricata1" do |surr1|
    surr1.vm.box = "generic/ubuntu1804"
    surr1.vm.hostname = "suricata1"
    surr1.vm.network :private_network, ip: "192.168.56.10"

    surr1.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbooks/deploy.yml"
    end
  end

  config.vm.define "appserver" do |surr2|
    surr2.vm.box = "generic/ubuntu1804"
    surr2.vm.hostname = "suricata2"
    surr2.vm.network :private_network, ip: "192.168.56.20"

  surr2.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbooks/deploy.yml"
    end
  end

end
