# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "server" do |machine|
    machine.vm.network "private_network", ip: "10.2.2.25"
    machine.vm.box = "ubuntu/bionic64"
    machine.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.verbose = 'vv'
      ansible.extra_vars = {
        github_token: ENV["PTA"]
      }
    end
  end
end
