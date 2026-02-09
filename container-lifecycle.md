Container lifecycle management  
A Docker container goes through multiple stages during its lifecycle. Understanding these stages helps in managing containers efficiently in cloud environments such as AWS, Azure, and GCP.  
  
Container lifecycle stages
1. Image creation - Before a container is created, a Docker image must exist.  
   docker build -t myapp:1.0 .  
Cloud Context:  
Images are built locally or in CI/CD pipelines  
Used across cloud providers
2. Container Creation - Creates a container but does not start it.  
   docker create --name mycontainer nginx  
Used when:  
Preparing containers before execution  
Debugging container configurations
3. Container Start - Starts the container  
   docker start mycontainer  
Cloud Context:  
Used in VM-based deployments  
Often automated via scripts
4. Show containers - containers that runs actively.  
   docker ps  
Used to:  
Monitor applications  
Verify service availability
5. Container stop - Stops a running container.  
   docker stop mycontainer  
Cloud Context:  
Used during application updates  
Prevents abrupt shutdowns
6. Container restart - Restarts a stopped or running container.  
   docker restart mycontainer  
Used for:  
Configuration changes  
Recovering failed applications
7. Container removal - Removes the stopped container  
   docker rm mycontainer  
Cloud Context:  
Frees compute and memory resources  
Important for cost optimization

---

Lifecycle in AWS, Azure, and GCP
1. Docker containers run on cloud VMs
2. Lifecycle commands remain the same
3. Cloud services manage infrastructure, Docker manages containers
