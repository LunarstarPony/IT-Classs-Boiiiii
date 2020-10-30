### System Platform: CentOS-7-x86_64-DVD-2003 Minimal Install Virtual Machine (Manual install vim)

### Using Nodetube https://github.com/mayeaux/nodetube

### Required Software: 
- Node.js 8.0+
- MongoDB
- Redis
- ffmpeg

### A, Installing Prerequisites

#### 1, Install Node.js

   A, We need to add yum repository by typing `sudo curl -sL https://rpm.nodesource.com/setup_10.x | sudo bash -`
   
   B, Once Repo is Installed, Type `sudo yum install nodejs` to install Node.js

#### 2, Install MongoDB

   A, Create a /etc/yum.repos.d/mongodb-org-4.4.repo file so that you can install MongoDB directly using yum
   
   Command: `sudo vim /etc/yum.repos.d/mongodb-org-4.4.repo`
      
      [mongodb-org-4.4]
      name=MongoDB Repository
      baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.4/x86_64/
      gpgcheck=1
      enabled=1
      gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc
      
    B, Install MongoDB by Typing `sudo yum install -y mongodb-org`
    
#### 3, Install Redis

   A, Enabling the Remi repository by running the following commands
   
   
      sudo yum install epel-release yum-utils
      sudo yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
      sudo yum-config-manager --enable remi

   B, Install Redis by typing `sudo yum -y install redis`
   
#### 4, Install FFmpeg

   A, The RPM Fusion repository depends on the EPEL software repository. If the EPEL is not enabled on your system, enable it by typing:
   
      sudo yum -y install epel-release
      
   B, Install RPM Fusion by typing 
   
      sudo yum localinstall --nogpgcheck https://download1.rpmfusion.org/free/el/rpmfusion-free-release-7.noarch.rpm
      
   C, Once the repo is enable, Install FFmpeg
   
      sudo yum install ffmpeg ffmpeg-devel
      
#### 5, Install git
   
   A, Install git by typing 
   
      sudo yum install git
     
#### 6, Enable and Start all the Service we just install

   A, Enable all the service by typing
      
      sudo systemctl enable mongod
      sudo systemctl enable redis
      
   B, Start all the service by typing
      
      sudo systemctl start mongod
      sudo systemctl start redis

### B, Install NodeTube

   1, Get the latest version of NodeTube by Typing 
   
      git clone https://github.com/mayeaux/nodetube
      
   2, Enter NodeTube folder that just created
   
      cd nodetube
      
   3,Install Node Modules
   
      npm install
      
   4,Just start our app!
   
      npm start
