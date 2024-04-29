# create EC2 instance
# Install Java
sudo apt install openjdk-11-jdk -y
# Add Jenkins Repository
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee   /usr/share/keyrings/jenkins-keyring.asc > /dev/null
# Add the Jenkins software repository to the source list and provide the authentication key:
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]   https://pkg.jenkins.io/debian-stable binary/ | sudo tee   /etc/apt/sources.list.d/jenkins.list > /dev/null
# Install Jenkins
sudo apt update
sudo apt install jenkins
sudo systemctl status jenkins
sudo apt-get install docker.io
sudo systemctl status docker
docker --version
sudo usermod -a -G docker $USER
sudo usermod -a -G docker jenkins
ssh-keygen
cat /var/lib/jenkins/secrets/initialAdminPassword