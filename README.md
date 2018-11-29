# Practica-09-Auditoria_Seguridad_Wordpress
###### La herramienta que vamos a utilizar para realizar la auditoría de nuestro sitio web WordPress es wpscan.
###### WPScan es un escáner de vulnerabilidad de WordPress de caja negra que se puede usar para escanear instalaciones remotas de WordPress para encontrar problemas de seguridad.

## Creación de Vagranfile
Creamos una carpeta donde van a estar ubicadas las maquinas virtuales.
Dentro de esa carpeta ejecutamos el comando mediante la consola ``vagrant init`` y se nos creara un archivo llamado ``Vagrantfile`` donde pondremos lo siguiente:
````
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
   cd /vagrant
   git clone https://github.com/wpscanteam/wpscan --depth 1
   cd wpscan
   sudo gem install -y bundler && bundle install --without test
   SHELL
end

````
## Usos básicos
Para comprobar si hay vulnerabilidades en los plugins de sitios WordPress:

``ruby wpscan.rb --url http://yourwebsite.com --enumerate vp``

Para comprobar si hay vulnerabilidades en los temas de sitios WordPress:

``ruby wpscan.rb --url http://yourwebsite.com --enumerate vt``

Para descubrir los logins de usuario del sitio:

``ruby wpscan.rb --url http://yourwebsite.com --enumerate u``



