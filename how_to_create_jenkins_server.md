# How to create a Jenkins Server:
--- 

### How to create a jenkinns server on a EC2 instance on AWS using Docker.

- https://docs.docker.com/engine/install/ubuntu/#set-up-the-repository 
- https://docs.docker.com/desktop/install/ubuntu/ 

AWS EC2 instance setup:

1. Name instance as you will example (Eng130-group1-jenkins-server)
2. You can either use an existing AMI or use ubuntu 18.04 LTS t2.micro instance
3. Security group set up should be as follows:
   <img width="1218" alt="Screenshot 2022-11-11 at 13 33 45" src="https://user-images.githubusercontent.com/115224560/201357235-e0241162-04b3-4cdf-ab54-2fe93f10ced4.png">

4. Then launch the instance.

You now have to SSH into the created EC2 instance for the server.

**Installing ubuntu on docker and docker**

Run the following commands in order

1. `sudo apt install gnome-terminal` For non-Gnome Desktop environments, gnome-terminal must be installed:
2. `sudo apt remove docker-desktop` Uninstall the tech preview or beta version of Docker Desktop for Linux. Run
3. `rm -r $HOME/.docker/desktop` optional
4. `sudo rm /usr/local/bin/com.docker.cli`optional
5. `sudo apt purge docker-desktop`optional
6. ```
    sudo apt-get update
    sudo apt-get install ./docker-desktop-<version>-<arch>.deb
   ```
7. `sudo apt-get update`

8. ```
    sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    ```
    
    ```
     sudo mkdir -p /etc/apt/keyrings
     curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
     ```
     ```
     echo \
     "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null 
     ```

### Install Docker Engine
- https://docs.docker.com/engine/install/ubuntu/#set-up-the-repository

- ` sudo apt-get update` Update the apt package index:
- `sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin` To install the latest version, run:
- `sudo docker run hello-world` Verify that the Docker Engine installation is successful by running the hello-world image:

### Install jenkins

- Doc on how to install jenkins 
- https://hub.docker.com/r/jenkins/jenkins 
- https://github.com/jenkinsci/docker/blob/master/README.md

- `sudo docker pull jenkins/jenkins:lts-jdk11`
`docker run -p 8080:8080 -p 50000:50000 --restart=on-failure jenkins/jenkins:lts-jdk11`


---

Now using the publick IP of the EC2 lauch jenkins by adding :8080 at the end 
- Example `http://34.251.46.96:8080/`
- You will be prompted with the following screen. 
<img width="1044" alt="Screenshot 2022-11-11 at 13 57 54" src="https://user-images.githubusercontent.com/115224560/201357084-14eca68f-5ab8-437c-b1d6-839f8730577d.png">

- The password can be found in your terminal 

- `Select plugins to install`
<img width="1058" alt="Screenshot 2022-11-11 at 13 58 14" src="https://user-images.githubusercontent.com/115224560/201357189-567e48fe-0987-4129-af88-1f107d5a287b.png">

