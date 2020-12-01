Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    config.vm.network "private_network", ip: "192.168.51.5"
    config.vm.synced_folder "src/", "/var/www/html/moodle", create: true
    config.vm.synced_folder "moodledata/", "/var/moodledata", create: true

    config.vm.provider "virtualbox" do |v|
        v.name = "Limu_Moodle"
        v.memory = 1024
        v.cpus = 1
    end

end