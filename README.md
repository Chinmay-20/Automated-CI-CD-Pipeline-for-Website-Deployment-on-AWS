Project Overview

This project demonstrates the setup of a CI/CD pipeline using Jenkins, Ansible, Docker, and GitHub webhooks on AWS EC2 instances. It includes the deployment of a static website built with HTML and CSS.

Architecture

EC2 Instances: Two t2.medium instances running Ubuntu 22.04.
Instance 1: Jenkins and Ansible.
Instance 2: Docker.
Key Technologies: Jenkins, Ansible, Docker, GitHub, AWS EC2.
Setup and Configuration

Prerequisites
AWS account with access to EC2.
GitHub account for source control.
EC2 Configuration
Create two t2.medium instances with Ubuntu 22.04.
Configure SSH keys for secure access.
Set inbound rules:
Jenkins instance: Allow HTTP and SSH traffic.
Docker instance: Allow traffic for web access and SSH.

Jenkins Configuration
Access Jenkins through your browser at `http://
2. Complete the initial setup by entering the admin password found in /var/lib/jenkins/secrets/initialAdminPassword.

Install the required plugins (e.g., Git, Ansible).
Set up a new job for the project, configuring it to trigger on GitHub webhook notifications.
GitHub Webhook Configuration
In your GitHub repository, go to Settings > Webhooks.
Click "Add webhook" and enter your Jenkins instance URL followed by /github-webhook/ (e.g., http://your-jenkins-instance-ip:8080/github-webhook/).
Choose "Just the push event" and save.
Ansible and Docker Workflow
Create an Ansible playbook (deployment.yaml) that:
Clones the repository.
Transfers the website files to the Docker instance.
Commands the Docker instance to build and run the container using the Dockerfile in the repository.

CI/CD Pipeline Execution
Any commit to the repository triggers the Jenkins job.
Jenkins executes the Ansible playbook which updates the Docker container.
The entire pipeline runs typically within 10 seconds.

Monitoring and Logs

Jenkins provides a console output for each build, accessible from the Jenkins dashboard.
Docker logs can be checked using docker logs [container_id] for troubleshooting.

Conclusion

This project illustrates a robust CI/CD pipeline for a static website, demonstrating modern DevOps practices with Jenkins, Ansible, Docker, and GitHub on AWS EC2.
![image4](https://github.com/Chinmay-20/ansible-jenkins-docker/assets/59417006/940af419-01df-4a1b-bd39-5d1a6f9c0de4)
![image3](https://github.com/Chinmay-20/ansible-jenkins-docker/assets/59417006/51fbc803-802e-4452-a172-e73ed14aef9a)
![image2](https://github.com/Chinmay-20/ansible-jenkins-docker/assets/59417006/5ef99ee3-339f-4d0a-b714-e65474faa318)
![image1](https://github.com/Chinmay-20/ansible-jenkins-docker/assets/59417006/629d7415-34a6-4313-a747-6048e157a2b6)


