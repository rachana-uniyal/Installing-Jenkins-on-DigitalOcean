# Installing-Jenkins-on-DigitalOcean

## Demo Project

**Install Jenkins on DigitalOcean**

**Technologies used:** Jenkins, Docker, DigitalOcean, Linux

**Project Description:**
- Create an Ubuntu server on DigitalOcean
- Set up and run Jenkins as a Docker container
- Initialize Jenkins

**Steps:**
1. Created a Server (Droplet) on DigitalOcean
2. Configured Firewall Rules to open port 22 and port 8080 for our new server
3. Installed Docker on DigitalOcean Droplet
    - `apt update`
    - `apt install docker.io`
4. Started Jenkins Docker container with named volume
    - `docker run -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts`
5. Initialized Jenkins
    - Access Jenkins on the browser: [http://64.227.170.131:8080/](http://64.227.170.131:8080/)
    - Access the one-time password
        - `docker exec -it 3ad844beaaab /bin/bash`
        - `cat /var/jenkins_home/secrets/initialAdminPassword`
