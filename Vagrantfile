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

            if i == 1
                node.vm.provision "shell", inline: <<-SHELL
                    sudo sed -i 's/://archive.ubuntu.com' /etc/apt/sources.list
                    sudo sed -i 's/://security.ubuntu.com' /etc/apt/sources.list
                
                    sudo apt-get update
                    sudo apt-get install -y ansible
                SHELL
            end 




        end    
    end
end