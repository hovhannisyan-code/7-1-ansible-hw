VAGRANTFILE_API_VERSION = "2"
ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "net1" do |vm1|
    vm1.vm.box = 'ubuntu/22.04'
    vm1.vm.host_name = "net1"
    vm1.vm.network "public_network", bridge: "enp3s0" 

    vm1.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--cpus", "2"]
      vb.customize ["modifyvm", :id, "--memory", "2000"]
    end
  end

  config.vm.define "net2" do |vm2|
    vm2.vm.box = 'ubuntu/22.04'
    vm2.vm.host_name = "net2"
    vm2.vm.network "public_network", bridge: "enp3s0"

    vm2.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--cpus", "2"]
      vb.customize ["modifyvm", :id, "--memory", "2000"]
    end
  end

end
