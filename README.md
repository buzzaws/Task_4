## Task 4: CI/CD Pipeline using Jenkins & GitHub
### Objective: Automate deployment using Jenkins with GitHub as the source repository

STEPS: 
i) Install and configure Jenkins on the EC2 instance.

#### command to install jenkins
sudo apt update

sudo apt install fontconfig openjdk-17-jre

java -version

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
  
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  
sudo apt-get update

sudo apt-get install jenkins


ii)Install necessary plugins (Git, Pipeline, Docker)

Access the jenkins via ip-address:8080

go to Manage jenkins

go to the plugin section

Install all necessary plugin like(Git server , Docker & Docker pipeline , Pipeline)


iii)  Set up a Jenkins pipeline to:

• Pull the latest code from GitHub.

• Build a new Docker image.

• Push the image to Docker Hub or AWS ECR.

• Deploy the updated container on the EC2 instance.


### Create Jenkinfile  for above steps

*** check the jenkinsfile for the above steps 


iv) Test the pipeline by making changes to the application and triggering an automated deployment.

v) Snapshot

<img width="1200" alt="Screenshot 2025-02-28 at 2 05 34 PM" src="https://github.com/user-attachments/assets/1cbe3bae-49e0-4949-987c-c236aa61355a" />


<img width="1200" alt="Screenshot 2025-02-28 at 1 27 44 PM" src="https://github.com/user-attachments/assets/aa02f4c9-1c0f-4192-9c7a-3c129ebf2011" />






