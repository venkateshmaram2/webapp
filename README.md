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

$wget https://api.bintray.com/content/jfrog/artifactory-rpms/jfrog-artifactory-oss/jfrog-artifactory-oss-$latest.rpm;bt_package=jfrog-artifactory-oss

$yum install -y jfrog-artifactory-oss-6.6.5.rpm

$echo "export ARTIFACTORY_HOME=/opt/jfrog/artifactory" >> /etc/profile

$./etc/profile or source /etc/profile

$env | grep ARTIFACTORY_HOME

$systemctl start artifactory.service

$systemctl enable artifactory.service


# Step 4: Install tomcat server on the above tomcat instance

$sudo yum update -y && sudo yum install wget -y && sudo yum install git -y

Step 2: install openjdk

sudo yum install java-1.8.0-openjdk-devel -y

Step 3: install set up tomcat app server

$sudo groupadd tomcat

$sudo useradd -M -s /bin/nologin -g tomcat -d /opt/tomcat tomcat

$sudo yum install wget -y

$wget https://downloads.apache.org/tomcat/tomcat-8/v8.5.57/bin/apache-tomcat-8.5.57.tar.gz

$sudo mkdir /opt/tomcat

$sudo tar xvf apache-tomcat-8*tar.gz -C /opt/tomcat --strip-components=1

$cd /opt/tomcat

$sudo chgrp -R tomcat /opt/tomcat

$sudo chmod -R g+r conf

$sudo chmod g+x conf

$sudo chown -R tomcat webapps/ work/ temp/ logs/

$sudo vi /etc/systemd/system/tomcat.service

[Unit]

Description=Apache Tomcat Web Application…

