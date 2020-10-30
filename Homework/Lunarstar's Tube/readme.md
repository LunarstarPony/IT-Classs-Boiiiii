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
   
   C, Verify the Node.js and npm Installation by typing `node --version` and `npm --version`

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
