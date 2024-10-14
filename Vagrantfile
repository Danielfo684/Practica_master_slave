Vagrant.configure("2") do |config|
  # Máquina mercurio
  config.vm.define "mercurio" do |mercurio|
    mercurio.vm.box = "ubuntu/bookworm64"
    mercurio.vm.network "private_network", ip: "192.168.57.101"
  end

  # Máquina venus (esclavo)
  config.vm.define "venus" do |venus|
    venus.vm.box = "ubuntu/trusty64"
    venus.vm.network "private_network", ip: "192.168.57.102"
  end

  # Máquina tierra (maestro)
  config.vm.define "tierra" do |tierra|
    tierra.vm.box = "ubuntu/trusty64"
    tierra.vm.network "private_network", ip: "192.168.57.103"
  end

  # Máquina marte (servidor de correo)
  config.vm.define "marte" do |marte|
    marte.vm.box = "ubuntu/trusty64"
    marte.vm.network "private_network", ip: "192.168.57.104"
  end
end