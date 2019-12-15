# vagrant-oswatcher
Vagrant environment for OSWatcher

## Requirements

- [Vagrant](https://www.vagrantup.com/) `>= 2.2.6`
- `Hyper-V`

## Setup

    git clone https://github.com/Wenzel/vagrant-oswatcher

Edit `vagrant-oswatcher/Vagrantfile` and set the local path to [`oswatcher`](https://github.com/Wenzel/oswatcher)'s repo

~~~Ruby
oswatcher_path = "/path/to/oswatcher"
~~~

## Usage

    cd vagrant-oswatcher
    vagrant up --provider hyperv
    
At this point you can either login to the machine with `vagrant ssh`,
or connect via Hyper-V manager and login to the desktop, since `XFCE` has been installed.

credentials: `vagrant/vagrant`

When you are done playing, you can simply `vagrant destroy` to tear down the machine.
