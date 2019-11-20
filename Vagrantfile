# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial32"
  config.vm.hostname = "plex-packager"
  config.vm.provision "file", source: "plex-packager", destination: "~/.local/bin/"
  config.vm.provision "file", source: "mkapkg-x32", destination: "~/.local/bin/mkapkg"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y -q jq
    cp /vagrant/motd /etc/motd
    cp /vagrant/{plex-packager,mkapkg-x32} /opt/
    chmod -x /etc/update-motd.d/{10-help-text,50-motd-news,90-updates-available,91-release-upgrade}
  SHELL
end
