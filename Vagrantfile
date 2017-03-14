# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/jessie64"

  config.vm.provision "ansible" do |ansible|
    ansible.extra_vars = { enable_apt_proxy: true }
    ansible.verbose = "v"
    ansible.playbook = "playbooks/enable_apt_proxy.yml"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.extra_vars = {
        user_name: "msn",
        user_ssh_pub_key_file: ENV['HOME']+"/.ssh/id_rsa.pub",
        user_passwd: "msntest123"
      }
    ansible.verbose = "v"
    ansible.playbook = "site.yml"
  end

end
