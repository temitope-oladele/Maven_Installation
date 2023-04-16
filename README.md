# Maven_Installation
This contains the simple process of installing maven on Linux Server
### Step 1: Create Maven Server
Create AWS server for maven: t2.medium of RedHat instance type is used for the purpose of this demostration and with ssh port-22 open on the instance.
### Step 2: Install Java
sudo hostnamectl set-hostname maven
sudo su - ec2-user
cd /opt
sudo yum install java-11-openjdk-devel java-1.8.0-openjdk-devel -y
### Step 3: Download Maven from the apatche maven repository, extract maven repository and rename it
sudo yum install wget nano tree unzip git -y
sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.0/binaries/apache-maven-3.9.0-bin.zip
sudo unzip apache-maven-3.9.0-bin.zip
sudo rm -rf apache-maven-3.9.0-bin.zip
sudo mv apache-maven-3.9.0/ maven
### Step 4: Set Environmental Varable
vi ~/.bash_profile  # and add the lines below
export M2_HOME=/opt/maven
export PATH=$PATH:$M2_HOME/bin
refresh the profile
source ~/.bash_profile
mvn -version
