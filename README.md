# Continous-Integration-Pipeline
Continous Integration Pipeline
## Introduction:

Creating a CICD Pipeline to clone the code from the Git Hub repository and adding it to the docker container further creating an image of that container and pushing it to the docker hub.

- Launch an instance.
- Connect the instance.
- Clone the git repository and view the contents in the repository.

- Install docker and check the version.

- Add the user to the docker group using the below commands.

sudo usermod -aG docker $USER

sudo systemctl restart docker

- Dockerfile that is in the project.


- Build the docker file using the following command **docker build notes-app .**

- Install java for Jenkins.

```
sudo apt update
sudo apt install fontconfig openjdk-17-jre
```
- Install Jenkins.

```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list> /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

- To start the Jenkins, copy the PublicIP of the instance and colon followed by the Jenkins port i.e 8080.

- Give a password and start the Jenkins. You will be landed to the Jenkins dashboard.

- Create a new job by clicking on Create a job, giving a name, and selecting the project type as the pipeline.
- Give descriptions, select github project.

- Choose the GitHub hook trigger for GITScm polling.

- Add the Jenkins user to the docker group, and restart .
- add an environment variable for pushing the image to the docker hub in Jenkins.

go to dashboard —>Manage Jenkins —>Security(Credentials) —>System(global)

- Click on pipeline syntax and create a secret text for password.


- Write the groovy syntax for cloning the code from gitHub, then build the code, push the image to docker and then finally deploy it on 8000 port.
- Add the 8000 port to the security group of the instances.

- The image with name notes-app is successfully pushed to the docker hub.

- When you hit the public IP of the instance followed by the port assigned.
- you will successfully land to the app page

## Summary

Finally the pipeline is successfully build.
