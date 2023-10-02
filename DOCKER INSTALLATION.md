# AWS
# DOCKER INSTALLATION
1  sudo apt update    
    2  sudo apt install -y     apt-transport-https     ca-certificates     curl     gnupg     lsb-release     jq    
    3  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg    
    4  echo   "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null    
    5  sudo apt update    
    6  sudo apt install -y docker-ce docker-ce-cli containerd.io    
    7  sudo usermod -aG docker $USER    
    8  sudo usermod -aG dockerxUSER    
    9  COMPOSE_VERSION=$(curl -s "https://api.github.com/repos/docker/compose/tags" | jq -r '.[0].name')    
   10  sudo curl -L "https://github.com/docker/compose/releases/download/${COMPOSE_VERSION}/docker-compose-$(uname -s)-$(uname -m)"   -o /usr/local/bin/docker-compose    
   11  sudo chmod +x /usr/local/bin/docker-compose    
# PULL IMAGES   
 1 docker pull hello-world    
 2 docker pull nginx    
 3 docker pull ubuntu/apache2    
 # PORT
 1 docker run --name mynginxl -p 80:80 -d nginx    
 2 docker run --name myapache -p 80:80 -d ubuntu/apache2    
 # KILL IMAGE
 docker kill mynginxl    
 # INSPECT
 1 docker images    
 2  docker inspect    
 
