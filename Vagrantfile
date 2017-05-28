# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define :jenkins do |jenkins|
    jenkins.vm.box = "ubuntu/trusty64"
    jenkins.vm.hostname = "jenkins"
    jenkins.vm.network :public_network
    jenkins.vm.provider "virtualbox" do |vbox|
      vbox.customize ["modifyvm", :id, "--cpus", "1"]
      vbox.customize ["modifyvm", :id, "--memory", "1024"]
      vbox.customize ["modifyvm", :id, "--name", "jenkins"]
    end
    jenkins.vm.provision :ansible do |ansible|
                      ansible.playbook = "tasks/main.yml"
  end
  end
end

