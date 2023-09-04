========================= Install git ==================================

sudo apt install git

======================== Install Docker ==============================

sudo apt update
sudo apt install docker.io

sudo usermod -aG docker $USER

========================= Jenkins Installation ======================:

Install Java   //Jenkins Require Java to run for installations.//

1) sudo apt update
2) sudo apt install openjdk-11-jre
3) java -version


Install Jenkins

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins

sudo usermod -aG docker jenkins

Login jenkins https<public IP>:8080

Get the administrator password and login using admin account. Change the password and install the required plugins.



================Install the required plugins in Jenkins ==============


Install the plugin from Manage Jenkins --> plugin --> Available plugins

Git plugin
Docker Pipeline plugin

restart jenkins:
from CLI: 
sudo systemctl restart jenkins

from GUI: 
http://<public-ip>:8080/restart 



================== Installation of Argo CD using operators ========================
Goto 
https://operatorhub.io/
Search for Argo CD and Install on Kubernetes cluster.
