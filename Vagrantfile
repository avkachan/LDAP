# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  
        config.vm.define "ldap_a" do |ldap_a|
        ldap_a.vm.box = "sbeliakou/centos-6.7-x86_64"
        ldap_a.vm.hostname = "ldap"
        ldap_a.vm.network "private_network", ip: "192.168.25.203"
	
        ldap_a.vm.provider "virtualbox" do |ldap_a|
		ldap_a.cpus = 1		
		ldap_a.memory = 2048
                ldap_a.name = "ldap_a"
                end
	ldap_a.vm.provision "shell", path: "ldap_a.sh"
        end
	
	config.vm.provision "ansible" do |ansible|
		ansible.playbook = 'ansible/provision.yml'
		ansible.verbose = 'vv'
end
end
