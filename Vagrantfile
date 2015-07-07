Vagrant.configure("2") do |config|
  config.vm.box = "centos6.5.3"
config.vm.box_url = "https://github.com/2creatives/vagrant-centos/" +
  "releases/download/v6.5.3/centos65-x86_64-20140116.box"
  config.vm.provider :virtualbox do |vb|
    vb.customize [ 'modifyvm', :id, '--memory', 1024 ]
  end
  config.vm.network "forwarded_port", guest: 80, host: 8080

  #config.vm.provision :shell, inline: "yum -y update"
  config.vm.provision :shell, inline: "yum -y install wget"
  config.vm.provision :shell, inline: 'wget --no-check-certificate --no-cookies - --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u45-b14/jdk-8u45-linux-x64.rpm'
  config.vm.provision :shell, inline: "sudo rpm -ivh jdk-8u45-linux-x64.rpm"

end
