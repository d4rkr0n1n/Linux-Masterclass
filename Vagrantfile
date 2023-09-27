IP_NETWORK="192.168.69."
MACHINE_IP=11

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.box_check_update = false
  config.vm.define "linux_machine" do |linux_machine|
    linux_machine.vm.box = "generic/rhel9"
    linux_machine.vm.hostname = "linux-machine"
    linux_machine.vm.network "private_network", ip: IP_NETWORK + "#{MACHINE_IP}"
    linux_machine.vm.provider :virtualbox do |v|
      v.memory = 4096
      v.name = "linux_machine"
      v.cpus = 2
    end
    linux_machine.vm.provision "bootstrap", type: "shell", run: "never" do |s|
      s.inline = "echo 'bootstrapping'"
    end
  end
end
