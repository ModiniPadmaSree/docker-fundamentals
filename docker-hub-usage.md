Working with Docker Hub \
Docker Hub is a centralized container registry that allows users to store, share, and manage Docker images. It integrates seamlessly with AWS, Azure, and GCP environments. \
Creating a Docker Hub Account
1. Visit https://hub.docker.com
2. Create an account
3. Verify email

---
1. Docker login \
In terminal, run `docker login` and enter the username, password or authentication token. \
 \
Cloud Context: \
Required on cloud VMs before pushing images \
Used in CI/CD pipelines.
2. Create an image locally with a sample html file and Dockerfile and build the image and verify the image. \
docker build -t app:latest . \
docker images
3. Tag image for docker hub \
docker tag app:latest username/app:latest \
4. Push image to hub \
docker push username/app:latest \
 \
Cloud Usage: \
Push from AWS EC2, Azure VM, or GCP VM \
Images become accessible globally
5. Pull image \
docker pull username/app:latest \
 \
Cloud Usage: \
Used in cloud deployments \
Required for scaling applications
6. Run \
docker run -d -p 8080:80 username/app:latest \
7. Verify if the container is successfully running \
http://ip-of-ec2:8080 \
The web page of index.html will appear
---
Docker Hub in AWS, Azure, and GCP \
AWS: Used with EC2, EKS \
Azure: Used with AKS, Azure VMs \
GCP: Used with GKE, Compute Engine \
Docker Hub acts as the image source for all platforms.
