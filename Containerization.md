# **Containerization**
1. sudo dnf config-manager --add-repo {docker website}
2. sudo dnf install -y docker-ce-cli containerd.io docker-compose-plugin
3. sudo systemctl start docker
4. sudo systemctl enable docker
5. sudo usermod -aG docker $USER
6. logout and log back in for changes to take effect
- docker --version
- docker run hello-world
- docker pull {hello-world or (image)}
### Containers
- docker ps
    - shows active containers
- docker ps -a
    - shows all containers
- docker stop {containerId} or {container name}
    - stops container
- docker rm {containerId} or {container name}
    - removes container
### Images
- docker images
    - shows a  list of images
- docker rmi {repository}
    - removes the image
### Storage
#### Temporary
- docker run -it --name {container name} ubuntu
    - -it interactive terminal
- docker start -it --name {container name} ubuntu
    - places you inside the container
- echo "Hello from Docker!" > /tmp/hello.txt
    - adds Hello from Docker into a file in /tmp/hello.txt
- exit
    - leaves the container and stops it
- docker start -i {container name}
- cat /tmp/hello.txt
    - outputs the text from the file
#### Volume
- docker volume create {volume name}
- docker run -id -v {volume name}:/{folder} --name {container name} ubuntu
    - -id runs the container detached
    - -v specifies the volume to mount
    - any data written into {folder} will be written and stored in the {volume name}
- docker exec -it {container name or id} bash
    - accesses the container
- docker volume list
    - lists the volumes
- docker volume rm {volume name}
- when a file is created in the {folder}, it should be stored in the volume, not the container
- for commands inside of bash look at Linux Fundamentals.
### Network
- docker network ls
    - lists the networks
- docker network create {network name}
- docker run -id --network {network name} --name {container name} ubuntu
    - creates and adds a container to a network 
- docker network inspect {network name}
    - shows the containers attached to the network
- docker network connect {network name} {container name or id}
    - connects a container to a network
- docker network disconnect {network name} {container name or id}
    - removes the container from the network
- docker network rm {network name}
#### Pinging in container
1. apt update
2. apt install -y iputils-ping
3. ping
### Port Mapping
- docker run -d -p 8080:80 {nginx, ubuntu, etc.(image)}
    - runs the image on port 8080
    - -P will run on any port that is free
    - can run more than one port
        - -p 8080:80 -p 1234:22