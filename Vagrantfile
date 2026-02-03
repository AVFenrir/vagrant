Vagrant.configure("2") do |config|
    config.vm.box="ubuntu/trusty64"

    (1..3).each do |i|
        config.vm.define "host-#{i}" do |node|
            node.vm.hostname="host-#{i}"
            node.vm.network "private_network", ip: "192.168.68.#{10+i}"

            node.vm.provider "virtualbox" do |vb|
                vb.memory= "1024"
                vb.name="Host-#{i}"
            end
        end    
    end
end