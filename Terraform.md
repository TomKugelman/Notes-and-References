# Install on Linux
wget https://releases.hashicorp.com/terraform/0.14.6/terraform_0.14.6_linux_amd64.zip ### 64-bit Terraform Download CLI
unzip terraform_0.14.6_linux_amd64.zip
sudo mv terraform /bin
rm terraform_0.14.6_linux_amd64.zip
terraform --version

