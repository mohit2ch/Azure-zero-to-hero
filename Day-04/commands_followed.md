### Enter the Vm
ssh -i <ssh_key_location | .pem file> <username>@<vm_public_ip>
Error : WARNING: UNPROTECTED PRIVATE KEY FILE! 
### Change permissions on private key
chmod 600 <ssh_key_location>
This will change the permission to oonly rw for wner and group and others have no permissions to read, write or execute
### Update vm pckages on first access
sudo apt update
## Run jenkins on VM
### Install JDK
sudo apt install openjdk-17-jre
### Check if installed correctly
sudo apt install openjdk-17-jre
Output: 
openjdk version "17.0.14" 2025-01-21
OpenJDK Runtime Environment (build 17.0.14+7-Ubuntu-124.04)
OpenJDK 64-Bit Server VM (build 17.0.14+7-Ubuntu-124.04, mixed mode, sharing)
### Install Jenkins-LT Release
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
### Enable. start, and get status of jenkins
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
