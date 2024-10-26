# Installing Docker from the official website. 
https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

`sudo apt-get update`  
`sudo apt-get install ca-certificates curl`  
`sudo install -m 0755 -d /etc/apt/keyrings`  
`sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc`  
`sudo chmod a+r /etc/apt/keyrings/docker.asc`  

# Add the repository to Apt sources:
The following command is in one line  
  
`echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null` 

# Updating system and installing Docker:  
`sudo apt-get update`  
`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`

# Checking if Docker works
`sudo docker run hello-world`
# Change the Docker to non-root user
Docs https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user 

`sudo groupadd docker`   
`sudo usermod -aG docker $USER`   
`newgrp docker`  
   
Checking of Docker works with current user  
   
`docker run hello-world`

# Docker common commands

- Run Docker Compose: `docker compose up -d` / `docker compose up`

- Check Docker Compose's volumens status: `docker compose ps -a` / `docker compose ps`

- Remove Docker's images: `docker rmi -f imageID1 imageID2 ...` (-f = force)

- Copy a file to the docker we want to: `docker cp file docker_id:/dir`

- Check Docker's images: `docker images -a`

- Remove all dangling (not tagged or associated with a container) containers, volumes, networks and images: `docker system prune`, for unused `docker system prune -a`

- Shows all unused local images: `docker images ls -f dangling=true`

- Shows all unused local volumes: `docker volume ls -f dangling=true`

- Remove all local volumes not used by at least one container: `docker volume prune`
  
- Enter to a Docker's volumen: `docker compose exec VolumenID sh` / `docker compose exec VolumenID bash`
