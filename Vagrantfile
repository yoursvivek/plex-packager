# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define :plexpackager do |plexpackager|
    plexpackager.vm.box = "ubuntu/xenial32"
    plexpackager.vm.hostname = "plex-packager"
    plexpackager.vm.provision "file", source: "plex-packager", destination: "~/.local/bin/"
    plexpackager.vm.provision "file", source: "mkapkg-x32", destination: "~/.local/bin/mkapkg"
    plexpackager.vm.provision "shell", inline: <<-SHELL
      export DEBIAN_FRONTEND=noninteractive
      apt-get update -q
      apt-get install -q -y jq
      cp /vagrant/motd /etc/motd
      cp /vagrant/{plex-packager,mkapkg-x32} /opt/
      chmod -x /etc/update-motd.d/{10-help-text,50-motd-news,90-updates-available,91-release-upgrade}
    SHELL
  end
end
