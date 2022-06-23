### start Symfony with Docker from ZERO 

# install docker engine
sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

sudo docker run hello-world


# install docker-compose 

sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version

## Post installation Docker 

sudo groupadd docker

sudo usermod -aG docker $USER

newgrp docker

docker run hello-world


### You successfully Installed the Docker!


###
###

# now you have to build the docker-compose.yml

you can find the best docker configuration for symfony by cloning the following repository

git clone https://github.com/parthpokar7/docker.git

### Build the Docker 

# run the Command in the folder from cmd :
    
    $ docker-compose build

    expected output: 
        Successfully built xxxxxxxxxxxx
        Successfully tagged docker_php:latest

    
# run the Docker

    $ docker-compose up