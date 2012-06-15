
Vagrant::Config.run do  | config |

 config.vm.box = "lucid32"
 config.vm.box_url = "http://files.vagrantup.com/lucid32.box"

 config.vm.network :hostonly, "33.33.33.14"
 config.vm.share_folder "htdocs" , "/var/www", "." , :nfs=>true
 
 config.vm.provision :chef_solo do |chef|
  chef.cookbooks_path="chef/cookbooks"


  chef.add_recipe('apt')
  chef.add_recipe "build-essential"
  chef.add_recipe "build-essential"
  
  chef.add_recipe("apache2")
  chef.add_recipe("apache2::mod_php5")

  chef.add_recipe("mysql")
  chef.add_recipe("mysql::server")
  
  chef.add_recipe("php")
  chef.add_recipe("php::module_mysql")

  chef.json = {
    "mysql" => { 
      "server_root_password" => "root"
    }
  }
 end 
end
