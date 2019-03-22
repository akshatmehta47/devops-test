Vagrant.configure("2") do |configure|

  configure.vm.box = "ubuntu/trusty64"

  configure.vm.provider "virtualbox" do |virtual|
    virtual.memory = 4096
    virtual.cpus = 2
  end

  configure.vm.provider "virtualbox" do |virtual|
    virtual.customize ["modifyvm", :id, "--cpuexecutioncap", "100"]
  end
  
  configure.vm.network "private_network", ip: "10.10.10.20"
  
  configure.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "devops-test.yml"
  end
end
