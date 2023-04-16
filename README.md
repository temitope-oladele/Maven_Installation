# Maven_Installation
This contains the simple process of installing maven on Linux Server
### Step 1: Create Maven Server
Create AWS server for maven: t2.medium of RedHat instance type is used for the purpose of this demostration and with ssh port-22 open on the instance.
### Step 2: Install Java
<div>
  <pre><code>sudo hostnamectl set-hostname maven</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo hostnamectl set-hostname maven')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

Change user to ec2-user
<div>
  <pre><code>sudo su - ec2-user</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo su - ec2-user')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

Our working directory is the 'opt' directory however, you could decide where your download the maven package
<div>
  <pre><code>cd /opt</code></pre>
  <button onclick="navigator.clipboard.writeText('cd /opt')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

Maven works in a java environment hence you have to download the jdk package
<div>
  <pre><code>sudo yum install java-11-openjdk-devel java-1.8.0-openjdk-devel -y</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo yum install java-11-openjdk-devel java-1.8.0-openjdk-devel -y')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

### Step 3: Download Maven from the apatche maven repository, extract maven repository and rename it
<div>
  <pre><code>sudo yum install wget nano tree unzip git -y</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo yum install wget nano tree unzip git -y')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

Then install the maven package in the opt directory
<div>
  <pre><code>sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.0/binaries/apache-maven-3.9.0-bin.zip</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.0/binaries/apache-maven-3.9.0-bin.zip')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

Extract the the maven package in the opt directory; then remove the zipped file to conserve space and then for convinience of use, you may rename your extracted file.
<div>
  <pre><code>sudo unzip apache-maven-3.9.0-bin.zip</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo unzip apache-maven-3.9.0-bin.zip')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

<div>
  <pre><code>sudo rm -rf apache-maven-3.9.0-bin.zip</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo rm -rf apache-maven-3.9.0-bin.zip')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

<div>
  <pre><code>sudo mv apache-maven-3.9.0/ maven</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo mv apache-maven-3.9.0/ maven')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

### Step 4: Set Environmental Varable

<div>
  <pre><code>vi ~/.bash_profile</code></pre>
  <button onclick="navigator.clipboard.writeText('vi ~/.bash_profile')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>
 
 ...and add the lines below
 
export M2_HOME=/opt/maven
export PATH=$PATH:$M2_HOME/bin

Refresh the profile with the command below:
<div>
  <pre><code>source ~/.bash_profile</code></pre>
  <button onclick="navigator.clipboard.writeText('source ~/.bash_profile')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

mvn -version
