# Docker 3-tier web application project.

# Project Architecture:
<img width="1723" height="665" alt="Screenshot 2026-01-13 204454" src="https://github.com/user-attachments/assets/31a7cce5-ac02-403c-958b-e387afb31ef7" />

## 1️⃣ Launch an AWS EC2 Instance

### - Created an EC2 instance on AWS with Ubuntu as the OS.

### - Configured security groups to allow SSH (port 22) and HTTP (port 80) access.
<img width="1919" height="837" alt="image" src="https://github.com/user-attachments/assets/4bee9e30-7e45-4749-8564-a113c9d4271a" /> <br><br><br>

## 2️⃣ Connect to EC2

### - Connected to the EC2 instance from my PC using PowerShell and the SSH key:
### - ssh -i "your-key.pem" ubuntu@EC2-Public-IP

<img width="1919" height="827" alt="image" src="https://github.com/user-attachments/assets/69b8a9d4-289b-4f42-a81e-a39361bce1ff" /> <br><br><br>


<img width="1919" height="835" alt="image" src="https://github.com/user-attachments/assets/5377cd13-bb12-49e6-9b06-b2e19c656fbb" /> <br><br><br>


## 3️⃣ Update the System

### - Updated packages and system repositories:
### - sudo apt-get update && sudo apt-get upgrade -y
<img width="1919" height="832" alt="image" src="https://github.com/user-attachments/assets/2736bee5-79cf-40b2-939a-9fc1adcd0e02" /> <br><br><br>

<img width="1916" height="829" alt="image" src="https://github.com/user-attachments/assets/02d48417-181e-494c-8504-97a10f6816f3" /> <br><br><br>


## 4️⃣ Install Docker

### - Installed Docker engine on the EC2 instance:

### - sudo apt install docker.io -y

<img width="1919" height="827" alt="image" src="https://github.com/user-attachments/assets/2e3d5dee-fa9b-4830-82e0-8588618d61f2" /> <br><br><br>

<img width="1919" height="834" alt="image" src="https://github.com/user-attachments/assets/aae78b33-d2ed-4dc7-ae24-b3593351d861" /> <br><br><br>

## - Checked Docker Status

<img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/16588f8e-560b-4b28-92b7-930294c1b375" /> <br><br><br>

## - Added current user to the Docker group for permissionless usage:

### - sudo usermod -aG docker $USER

<img width="1919" height="832" alt="image" src="https://github.com/user-attachments/assets/cbf6cf77-e6a5-4cb7-8899-4bd2435fb8a6" /> <br><br><br>

## - Made a new directory for the project

<img width="1919" height="835" alt="image" src="https://github.com/user-attachments/assets/acce3a44-5032-4d95-9251-4e441b2e9a7b" /> <br><br><br>

## - Cloned the code from my Github repository. 

<img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/20b4cc47-2c60-4927-a4e5-c3439d4693b4" /> <br><br><br>

## - 5️⃣ Create Dockerfiles

### - Django App: Wrote a Dockerfile to containerize the backend application.

<img width="1919" height="835" alt="image" src="https://github.com/user-attachments/assets/3f840175-35c7-4343-8f6d-c8152718c523" /> <br><br><br>

### - Nginx: Wrote a Dockerfile and configuration files to act as a reverse proxy directing requests to Django.

<img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/5d3d825a-6a6d-42ca-a933-08e53036ae56" /> <br><br><br>

<img width="1919" height="830" alt="image" src="https://github.com/user-attachments/assets/69d5cb1d-b710-410e-948a-7d10dc6f7847" />

## - 6️⃣ Write Docker Compose File

### - Created a docker-compose.yml file to define all three containers (Nginx, Django, MySQL) and their networking:

### - Linked Nginx to Django backend

### - Linked Django to MySQL database

### - Exposed required ports for web access 

<img width="1919" height="836" alt="image" src="https://github.com/user-attachments/assets/932aa7f0-76c8-4054-bfe4-1b9bda706e04" />
<img width="1914" height="683" alt="image" src="https://github.com/user-attachments/assets/17fc5952-cf21-48d3-98bb-c33db2ad3c24" />
<img width="1897" height="305" alt="image" src="https://github.com/user-attachments/assets/c7463e18-8921-4bcb-b602-614cbd2f64d8" />


## - Installed the Docker Compose

<img width="1916" height="764" alt="image" src="https://github.com/user-attachments/assets/b8a48cb8-5174-4428-bb62-b988f5353055" /> <br><br><br>


## 7️⃣ Launch the Application

### - Started all containers at once using:

### - docker compose up -d




<img width="1919" height="834" alt="image" src="https://github.com/user-attachments/assets/159f91f7-0753-4891-9f27-a1849fe016f9" /> <br><br><br>

<img width="1919" height="826" alt="image" src="https://github.com/user-attachments/assets/1419002c-20f7-422f-b131-cc2d95560941" /> <br><br><br>

<img width="1919" height="825" alt="image" src="https://github.com/user-attachments/assets/961539a8-2280-4931-b924-f5d1531d44a0" /> <br><br><br>
<img width="1919" height="825" alt="image" src="https://github.com/user-attachments/assets/f60c5b98-bc52-498f-afb3-b21a0f1688e6" /> <br><br><br>

<img width="1919" height="830" alt="image" src="https://github.com/user-attachments/assets/bd26aa22-ffc0-49b0-b982-8a6a9a033dde" /> <br><br><br>


## 8. The web application became live instantly on AWS, with:

### - Nginx routing requests to Django

### - Django handling backend logic

### - MySQL storing and retrieving application data

<img width="1919" height="949" alt="image" src="https://github.com/user-attachments/assets/328fd360-75d7-421c-9065-f664499788ac" /> <br><br><br>

<img width="1919" height="944" alt="image" src="https://github.com/user-attachments/assets/6d1deccf-8f8f-4269-8fc1-6edfe2bed7d6" />


