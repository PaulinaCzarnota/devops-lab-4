Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  config.vm.network "forwarded_port", guest: "8080", host: 8082

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt upgrade -y
    apt install -y build-essential git dh-autoreconf libcurl4-gnutls-dev \
      libexpat1-dev gettext libz-dev libssl-dev \
      fontconfig openjdk-17-jre
    wget -O /usr/share/keyrings/jenkins-keyring.asc \
        https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
    echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
      https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
      /etc/apt/sources.list.d/jenkins.list > /dev/null
    apt update
    apt install -y jenkins
    systemctl enable jenkins
    systemctl start jenkins
  SHELL
end
