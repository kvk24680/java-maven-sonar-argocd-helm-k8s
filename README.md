# Jenkins Pipeline for Java based application using Maven, SonarQube, Argo CD, Helm and Kubernetes
A project which demostrates an end-to-end CI CD Pipeline

Step 1: Setup Jenkins

Install Java
sudo apt update
sudo apt install openjdk-11-jre

Verify Java is Installed

java -version

Now, you can proceed with installing Jenkins

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

**Note: ** By default, Jenkins will not be accessible to the external world due to the inbound traffic restriction by AWS. Open port 8080 in the inbound traffic rules

Check if Jenkins is running
ps -ef | grep jenkins

Access Jenkins in browser
<Instance Public IP> : 8080

Log In to Jenkins using Initial Admin Password and Install default plugins
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

Step 2: Write a pipeline in Jenkins

1. Select Pipeline and select Pipeline script from SCM
2. Create a Jenkinsfile inside Spring-boot-app directory
