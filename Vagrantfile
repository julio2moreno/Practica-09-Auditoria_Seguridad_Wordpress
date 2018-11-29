# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"

   config.vm.provision "shell", inline: <<-SHELL
   apt-get update
   apt-get install -y git
   Apt-get install –y ruby-bundler
   Apt-get install –y build-essential
   Apt-get install –y patch
   Apt-get install –y ruby-dev
   Apt-get install –y zliblg-dev
   Apt-get install –y liblzma-dev
   gem install nokogiri
   #apt-get install -y ruby-bundler
   #gem install nokiri -v '1.8.5'og 
   cd /vagrant
   git clone https://github.com/wpscanteam/wpscan --depth 1
   cd wpscan
   sudo gem install -y bundler && bundle install --without test
   #bundle install && rake install
   SHELL
end
