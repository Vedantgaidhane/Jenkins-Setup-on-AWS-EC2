# Setting Up Jenkins on AWS EC2

This repository contains a detailed guide and necessary scripts to set up Jenkins on an AWS EC2 instance. Follow the steps below to get Jenkins up and running on your own server.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Step-by-Step Guide](#step-by-step-guide)
  - [1. Create an EC2 Instance](#1-create-an-ec2-instance)
  - [2. Connect to the EC2 Instance](#2-connect-to-the-ec2-instance)
  - [3. Install Java JDK](#3-install-java-jdk)
  - [4. Add Jenkins Repository and Install Jenkins](#4-add-jenkins-repository-and-install-jenkins)
  - [5. Open Port 8080](#5-open-port-8080)
  - [6. Unlock Jenkins](#6-unlock-jenkins)
  - [7. Set Up Jenkins](#7-set-up-jenkins)
- [Scripts](#scripts)
- [Images](#images)
- [Contributing](#contributing)

## Prerequisites

- An AWS account
- Basic knowledge of AWS EC2
- MobaXterm or another SSH client
- Internet connection

## Step-by-Step Guide

### 1. Create an EC2 Instance

Launch a new EC2 instance using Amazon Linux 2 AMI. Choose an instance type that fits your workload requirements. Follow the [AWS documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html) for detailed steps.

![EC2 Instance Creation](images/1.png)



### 2. Connect to the EC2 Instance

Use MobaXterm or another SSH client to connect to your EC2 instance securely using your private key.

![MobaXterm Connection](images/mobaxtream.png)



### 3. Install Java JDK

Update the package lists and install the Java Development Kit (JDK):

```bash
sudo apt update
sudo apt install openjdk-11-jre
```



### 4. Add Jenkins Repository and Install Jenkins

Import the Jenkins repository key and add the repository. Then, update the package lists and install Jenkins:

```bash
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```



### 5. Open Port 8080
Edit the security group inbound rules to allow traffic on port 8080.
![Edit Inbound Rules](images/4.png)



### 6. Unlock Jenkins
Retrieve the initial administrative password to unlock Jenkins:
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
![Edit Inbound Rules](images/5.png)


### 7. Set Up Jenkins
Access Jenkins through your browser by navigating to the public IP address of your EC2 instance followed by port 8080. Follow the setup wizard to install recommended plugins and create an admin user account.
![Edit Inbound Rules](images/ip.png)


