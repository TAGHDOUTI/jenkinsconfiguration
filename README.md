# jenkinsconfiguration
This is a jenkins configuration for the first installation in AWS
Before installing jenkins Make sure to install JAVA and MAVEN in your EC2-instance

Installation of Jenkins : 

wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo

rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

yum install jenkins

service jenkins start

cat /var/lib/jenkins/secrets/initialAdminPassword

service jenkins start

yum remove jenkins

rm -rf /var/lib/jenkins

Java Path:

/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-0.amzn2.0.1.x86_64

Maven Path:

/usr/share/maven

Git Path:

/usr/bin/git

Assign Root User and Permissions to jenkins:

vi /etc/sysconfig/jenkins ==> Change in this file : JENKINS_USER="jenkins" TO ==> JENKINS_USER="root" And save it .

Run those comande in the terminal:

chown -R root:root /var/lib/jenkins
chown -R root:root /var/cache/jenkins
chown -R root:root /var/log/jenkins

service jenkins restart


Tomcat Installation and Integration:

yum install tomcat

yum install tomcat-webapps tomcat-admin-webapps 

vi /usr/share/tomcat/conf/tomcat-users.xml

Uncomment Admin roles and user and Add:

<user username="deployer" password="deployer" roles="manager-script" />

Deploy war/ear to a container:

**/java-web-project.war


EDITED BY : BILAL TAGHDOUTI    


![image](https://user-images.githubusercontent.com/62719460/115116181-d782b180-9f87-11eb-80f0-9a02daf00923.png)
