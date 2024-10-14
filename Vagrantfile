Vagrant.configure("2") do |config|
  # Máquina venus (esclavo)
  config.vm.define "venus" do |venus|
    venus.vm.box = "debian/bullseye64"
    venus.vm.hostname = "venus.sistema.test"
    venus.vm.network "private_network", ip: "192.168.57.102"
    venus.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y bind9 dnsutils

sudo cp /vagrant/venus-conf/named.conf.local /etc/bind/named.conf.local
    SHELL
  end

  # Máquina tierra (maestro)
  config.vm.define "tierra" do |tierra|
    tierra.vm.box = "debian/bullseye64"
    tierra.vm.hostname = "tierra.sistema.test"
    tierra.vm.network "private_network", ip: "192.168.57.103"
    tierra.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y bind9 dnsutils
      sudo cp /vagrant/tierra-conf/named.conf.local /etc/bind/named.conf.local
      sudo cp /vagrant/tierra-conf/named.conf.options /etc/bind/named.conf.options
      sudo cp /vagrant/tierra-conf/db.sistema.test /etc/bind/db.sistema.test
      sudo cp /vagrant/tierra-conf/db.192 /etc/bind/db.192
    SHELL
  end
end

