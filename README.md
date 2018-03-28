# test_docker_nginx_wordpress

for run this project you must run some options
Exemple for Ubuntu 16.04

Step 1 - Install Docker
Before we begin, update the Ubuntu repository and install latest updates:

sudo apt-get update and sudo apt-get upgrade
When the installation is done, start docker and add it to start automatically at boot time:

        systemctl start docker
        systemctl enable docker

Step 2 - Install Docker-Compose

Docker-compose Python script and if we need to install it we must:
        sudo apt-get install -y python python-pip
        pip install docker-compose

check the docker-compose from the command:
        docker-compose -v

Step 3 - Create some folders
For out project we need some folders create it:

        mkdir -p db-data/
        mkdir -p logs/nginx/
        mkdir -p wordpress/

Step 4 - Create accounts in papertrial and datadog
Create accounts on https://papertrailapp.com and https://www.datadoghq.com. Add from datadog you API_KEY to docker-compose.yml in datadog section. 
From papetrialapp chose integration with Docker-Compose and paste your "udp://logsN.papertrailapp.com:XXXXX" in syslog-addres those containers which you want to receive the logs in this project add to nginx and mysql in section logging.

Step 5 - Run Docker-compose
Start to create the new containers with docker compose. Go to the project directory and start the new containers based on our compose file:

        docker-compose up -d
