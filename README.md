# Continuous Integration - Conitinuous Delivery - Continuous Deployment

Step 1: Launch 3 instances with names  jenkins, artifactory and tomcat
Note down public ips
jenkins -
artifactory -
tomcat - 


Step 2: Install jenkins server on the above jenkins instance

$sudo yum install java-1.8.0-openjdk-devel

$curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo

$sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

$sudo yum install jenkins

$sudo systemctl start jenkins

$sudo systemctl enable jenkins

