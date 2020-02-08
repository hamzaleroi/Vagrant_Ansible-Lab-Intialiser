Vagrant.configure("2") do |config|
    config.vm.define "vagrant1" do |vagrant|
        vagrant.vm.box = "ubuntu/trusty64"
        vagrant.vm.network "private_network", ip: "192.168.43.100"
    end
    config.vm.define "vagrant2" do |vagrant|
        vagrant.vm.box = "ubuntu/trusty64"
        vagrant.vm.network "private_network", ip: "192.168.43.101"
    end
    config.vm.define "vagrant3" do |vagrant|
        vagrant.vm.box = "ubuntu/trusty64"
        vagrant.vm.network "private_network", ip: "192.168.43.102"
        vagrant.vm.provision "ansible" do |ansible|
            ansible.playbook="setup.yml"
            ansible.vault_password_file = "password"
            ansible.limit = "all"
            # ansible.tags= ["setting_facts","gather","register"]
    
        end
    end
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 256
    end
    
    # Network settings:
    # config.vm.network "forwarded_port", guest: 80, host: 8080

    # Folder settings :
    # config.vm.synced_folder ".", "/var/www/html", :nfs => { :mount_options => ["dmode=777", "fmode=666"]}
    # Provision settings
    # config.vm.provision "shell", inline: <<-SHELL
      #  apt-get update
       # apt-get install -y apache2
        # don't need root cuz it's gonna be executed as root
    # SHELL

    # config.vm.provision "shell", path: "bootstrap.sh"

end





# vagrant commands:

# vagrant up
# vagrant destroy
# vagrant resume
# vagrant reload
# vagrant suspend


# vagrant ssh
