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

![EC2 Instance Creation](images/ec2-instance-creation.png)

### 2. Connect to the EC2 Instance

Use MobaXterm or another SSH client to connect to your EC2 instance securely using your private key.

![MobaXterm Connection](images/mobaxtrem-connection.png)

### 3. Install Java JDK

Update the package lists and install the Java Development Kit (JDK):

```bash
sudo apt update
sudo apt install openjdk-11-jre

