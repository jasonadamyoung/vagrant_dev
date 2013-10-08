# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise64"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  config.vm.box_url = " http://files.vagrantup.com/precise64_vmware.box"

  # pump up the volume
  config.vm.provider :vmware_fusion do |v|
    v.vmx["memsize"] = "2048"
  end

  # networking via vagrant-dns
  config.dns.tld = "vdev"
  config.vm.hostname = "railsdev"
  config.vm.network :private_network, ip: "192.168.42.42"


  # ansibilate
  config.vm.provision :ansible do |ansible|
    ansible.verbose = 'vv'
    ansible.sudo = true
    ansible.playbook = "provisioning/setup.yml"
  end

end
