# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.6"

  config.vm.define 'inspirational-message-repeater' do |node|
    node.vm.hostname = 'inspirational-message-repeater'
  end # or one line with `config.vm.define "inspirational-message-repeater"`

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "/vagrant/inspirational.yml"
    ansible.groups = {
      "web_servers" => ["inspirational-message-repeater"]
    }
    # Uncomment this if you need more verbose output from Ansible
    # ansible.verbose = vv
  end
end
