Docker provides a set of commands to manage container images and containers. These commands remain the same across cloud platforms such as AWS, Azure, and GCP because Docker runs on virtual machines or managed Kubernetes nodes in all these environments. \
Prerequisites \
- Linux VM (AWS EC2 / Azure VM / GCP Compute Engine)
- Docker installed and running
- User added to Docker group. \
This document explains commonly used Docker commands with examples and cloud usage context. \
1. `docker pull` - The docker pull command downloads a Docker image from a container registry such as Docker Hub. \
    docker pull <image-name>:<tag> \
    Ex: docker pull nginx:latest \
Cloud Usage \
AWS: Pull images on EC2 instances or EKS worker nodes \
Azure: Used on Azure VM or AKS nodes \
GCP: Used on Compute Engine VM or GKE nodes
2. `docker run` - The docker run command creates and starts a container from a Docker image. \
    docker run [options] <image-name> \
    Ex: docker run -d -p 80:80 nginx \
Cloud Usage \
Runs applications inside cloud VMs \
Used for testing applications before deploying to Kubernetes \
Common for running monitoring tools and microservices
3. `docker ps` - The docker ps command lists running containers. \
    Ex: docker ps -a \
Cloud Usage \
Verify running containers on cloud VMs \
Used during debugging and monitoring
4. `docker stop` - Stops a running container \
    docker stop <container-id> \
    Ex: docker stop nginx-container \
Cloud Usage \
Used during deployments and updates \
Helps manage application downtime on cloud servers
5. `docker rm` - Delete stopped containers \
    docker rm <container-id> \
    Ex: docker rm nginx-container \
Cloud Usage \
Frees resources on cloud VMs \
Used in automation scripts and CI/CD pipelines
6. `docker rm -f` - Force stops and remove container \
    Ex: docker rm -f nginx-container
