# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

	config.omnibus.chef_version = :latest

	config.vm.box = "opscode-ubuntu-14.04"
	config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.04_chef-provisionerless.box"

    config.vm.network "forwarded_port", guest: 80, host: 8080

    config.vm.network :private_network, ip: "192.168.58.100"

    #config.vm.synced_folder ".", "/vagrant"

    config.vm.provider :virtualbox do |vb|
        vb.gui = false
        vb.customize ["modifyvm", :id, "--name", "opscode-ubuntu-14.04", "--memory", "1024"]
    end

    config.vm.provision "chef_solo" do |chef|
    chef.cookbooks_path = "./devops/chef/cookbooks"


        chef.add_recipe "apt"
        chef.add_recipe "vim"
        chef.add_recipe "openssl"
        chef.add_recipe "apache2"
        chef.add_recipe "apache2::mod_rewrite"
        chef.add_recipe "apache2::mod_ssl"
        chef.add_recipe "apache2::mod_php5"
        chef.add_recipe "mysql::server"
        chef.add_recipe "php"
        chef.add_recipe "php::module_mysql"
        chef.add_recipe "php::module_apc"
        chef.add_recipe "php::module_gd"
        chef.add_recipe "php::module_curl"

        chef.json = {
            "mysql" => {
                "server_root_password"      => "",
                "server_repl_password"      => "",
                "server_debian_password"    => ""
            }
        }

    end

end
