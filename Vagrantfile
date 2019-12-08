Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu1804"
  config.vm.box_version = "2.0.6"
  # OSWatcher local git repo
  oswatcher_path = "/path/to/oswatcher"

  config.vm.provider "hyper-v" do |hyperv|
    hyperv.vmname = "oswatcher"
    hyperv.cpus = 2
    hyperv.memory = 2048
    # allow nested virtualization
    hyperv.enable_virtualization_extensions = true
  end

  config.vm.synced_folder ".", "/vagrant"
  # make oswatcher local path accessible as /vagrant/oswatcher
  config.vm.synced_folder oswatcher_path, "/vagrant/oswatcher"

  config.vm.provision "ansible_local" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "ansible/playbook.yml"
    ansible.extra_vars = {
      'oswatcher_path': "/vagrant/oswatcher",
    }
  end
end
