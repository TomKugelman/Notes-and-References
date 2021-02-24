# Install Docker on Linux
## These packages are required for Docker
sudo apt install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

## Add GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

## Add docker repo to apt
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

## Update apt
sudo apt update

## Download the three docker packages (this has containerd, not docker-engine which is deprecated)
sudo apt install docker-ce docker-ce-cli containerd.io

## Change permissions on the docker daemon socket
sudo chmod 777 /var/run/docker.sock