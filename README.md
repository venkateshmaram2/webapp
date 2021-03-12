# Continuous Integration - Conitinuous Delivery - Continuous Deployment

# Step 1: Launch 3 instances with names  jenkins, artifactory and tomcat

Note down public ips

jenkins -

artifactory -

tomcat - 


# Step 2: Install jenkins server on the above jenkins instance

$sudo yum install java-1.8.0-openjdk-devel

$curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo

$sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

$sudo yum install jenkins

$sudo systemctl start jenkins

$sudo systemctl enable jenkins

Access jenkins server:  http://<PUBLIC_IP>:8080


# Step 3: Install Artifactory server on the above attifactory instance

$yum install -y java-1.8.0-openjdk-devel

$sudo chmod 777 /etc/profile

$sudo echo "export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.191.b12-1.el7_6.x86_64" >> /etc/profile

$source /etc/profile

$env | grep JAVA

$yum install -y net-tools rsync

$wget https://bintray.com/jfrog/artifactory-rpms/rpm -O bintray-jfrog-artifactory-rpms.repo

$sudo mv bintray-jfrog-artifactory-rpms.repo /etc/yum.repos.d/

$ sudo yum install jfrog-artifactory-oss

$sudo echo "export ARTIFACTORY_HOME=/opt/jfrog/artifactory" >> /etc/profile

$source /etc/profile

$env | grep ARTIFACTORY_HOME

$systemctl start artifactory

$systemctl enable artifactory

$systemctl status artifactory

acess artifactory  server  http://<public ip>:8081



# Step 4: Install tomcat server on the above tomcat instance

$sudo yum update -y && sudo yum install wget -y && sudo yum install git -y

Step 2: install openjdk

sudo yum install java-1.8.0-openjdk-devel -y

Step 3: install set up tomcat app server

$wget https://downloads.apache.org/tomcat/tomcat-8/v8.5.64/bin/apache-tomcat-8.5.64.tar.gz

$mkdir tomcat

$sudo tar xvf apache-tomcat-8*tar.gz -C /home/centos/tomcat --strip-components=1

$sudo chown -R centos:centos /home/centos/tomcat/*

$sudo sh /home/centos/tomcat/bin/startup.sh
