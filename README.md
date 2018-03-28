# test_docker_nginx_wordpress

for run this project you must run some options
Exemple for Ubuntu 16.04

Step 1 - Install Docker
Before we begin, update the Ubuntu repository and install latest updates:

        sudo apt-get update
        sudo apt-get upgrade
        sudo apt-get install -y docker.io


When the installation is done, start docker and add it to start automatically at boot time:

        systemctl start docker
        systemctl enable docker

Step 2 - Install Docker-Compose

Docker-compose Python script and if we need to install it we must:

        sudo apt-get install -y python python-pip
        pip install docker-compose

check the docker-compose from the command:

        docker-compose -v

Step 3 - Create accounts in papertrial and datadog
Create accounts on https://papertrailapp.com and https://www.datadoghq.com. Add from datadog you API_KEY to docker-compose.yml in datadog section. 
From papetrialapp chose integration with Docker-Compose and paste your "udp://logsN.papertrailapp.com:XXXXX" in syslog-addres those containers which you want to receive the logs in this project add to nginx and mysql in section logging.

Step 4 - Run Docker-compose
Start to create the new containers with docker compose. Go to the project directory and start the new containers based on our compose file:

        docker-compose up -d

Step 5 - Install Wordpress

Before we do this step, let's check the ports/open ports on the system. For work our project we have 3 ports opened, port 80, 3306 and port 9000.Run command:

        netstat -plntu

If this ports are open you mast open your web browser and type in the server URL or IP address.

http://localhost/
all
127.0.0.1
You can see the WordPress installation page. Choose your language and click 'Continue'.
Fill in your website details:
site title, admin user and password, your email address and then click 'Install Wordpress'.

