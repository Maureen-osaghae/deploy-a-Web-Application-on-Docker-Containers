# ☁️ Migrate a Web Application to Docker Containers

## 🧭 Project Overview
This project demonstrates the migration of a web application from Amazon EC2 instances (running on guest OS) to Docker containers.  
The migration included containerizing both the **Node.js web application** and the **MySQL database**, and publishing the Docker images to **Amazon Elastic Container Registry (ECR)**.

### 🔍 Objectives
- Create a `Dockerfile` and build Docker images.
- Run and manage containers from Docker images.
- Configure container networking and environment variables.
- Migrate MySQL database into a container.
- Push Docker images to **Amazon ECR** for scalable deployment.

---

## 🏢 Business Scenario

The café owners have expanded their business by acquiring a coffee supplier that maintains an inventory tracking web app hosted on AWS EC2.  
My role was to **migrate this legacy web application into containers** to enable better scalability, portability, and simplified DevOps management.

---

## 🧱 Architecture Overview

### Before Migration
The app and MySQL database were hosted on separate EC2 instances.

![Before Migration Architecture](https://github.com/user-attachments/assets/44cbcaec-2221-4877-8102-159b780cdb7e)

### After Migration
Both the app and database now run in Docker containers and are registered in Amazon ECR for future deployments.

![After Migration Architecture](https://github.com/user-attachments/assets/765ceecd-d8f1-40db-8711-7f346bf7b3db)

---

## 🧰 Key Implementation Steps

### 1️⃣ Setting Up the Development Environment
- Connected to AWS Cloud9 / VS Code IDE for the lab setup.  
- Downloaded and extracted the project files.
- Upgraded AWS CLI and Python packages for Docker integration.

![VS Code Setup](https://github.com/user-attachments/assets/64e1e463-6df0-4f80-b1f1-79393f064b09)

---

### 2️⃣ Analyzing Existing Infrastructure
- Reviewed the coffee supplier’s EC2-based app and verified database connectivity.
- Inspected running EC2 instances (`AppServerNode`, `MysqlServerNode`, and IDE instance).

![EC2 Instances](https://github.com/user-attachments/assets/430351f3-e843-4cbf-ac04-c85bad8b3969)
![Web App Before Migration](https://github.com/user-attachments/assets/c8028790-ffef-4654-9f53-b206714db299)

---

### 3️⃣ Migrating the Node.js Application to Docker
- Built a Docker image using a custom `Dockerfile`.
- Ran the container exposing port `3000`.
- Configured environment variables for DB connectivity.

![Dockerfile Setup](https://github.com/user-attachments/assets/b0985c66-042f-4bed-8121-76e85c3d0c80)
![Node App Container Running](https://github.com/user-attachments/assets/dd91fd43-d9ca-42a3-abfe-2985df7db2f7)
![App Running on Port 3000](https://github.com/user-attachments/assets/59440489-b35c-4e14-81f8-61b658fff0b6)

---

### 4️⃣ Migrating MySQL Database to Docker
- Created a `mysqldump` of the existing database.
- Built and ran a new MySQL container using that dump file.
- Configured network and credentials for app-to-db communication.

![MySQL Dump File](https://github.com/user-attachments/assets/05f03333-bb73-4e03-af65-6879702d9009)
![MySQL Dockerfile](https://github.com/user-attachments/assets/7d61b44e-3702-4f39-916e-3a9cbf1dec02)
![MySQL Container Running](https://github.com/user-attachments/assets/616a519f-5b2b-43c6-879d-91a69501d980)
![Database Connectivity Successful](https://github.com/user-attachments/assets/358f6987-bf73-4ae0-8972-dee49e8635bd)

---

### 5️⃣ Pushing Docker Images to Amazon ECR
- Created an ECR repository named `node-app`.
- Tagged and pushed the Docker images.
- Verified image upload in the AWS ECR console.

![ECR Authentication](https://github.com/user-attachments/assets/afdb598c-54c7-4bdb-a413-5dc4f62ed23a)
![ECR Repository](https://github.com/user-attachments/assets/74867b81-6779-44f9-8543-92f107933ca9)
![Image Tagging](https://github.com/user-attachments/assets/9124672e-3c7c-4430-8280-d1d9abefaf2c)
![Image Upload](https://github.com/user-attachments/assets/367d0e40-7965-4d52-b18a-7204f476dbdc)

---

## 📊 Results

✅ Successfully migrated both **Node.js** web app and **MySQL** database into Docker containers.  
✅ Validated seamless connectivity between containers.  
✅ Registered Docker images in **Amazon ECR** for future CI/CD integration with AWS Elastic Beanstalk.  
✅ Improved scalability, portability, and deployment efficiency.

---

## 🧩 Tools & Technologies

| Category | Tools |
|-----------|-------|
| **Cloud** | AWS EC2, ECR |
| **Containers** | Docker, Docker Compose |
| **Languages** | Node.js, SQL |
| **Database** | MySQL |
| **Version Control** | GitHub |
| **Dev Tools** | VS Code, AWS CLI |

---

## 📸 Proof of Work Gallery

| Step | Screenshot |
|------|-------------|
| App Architecture Before Migration | ![Before](https://github.com/user-attachments/assets/44cbcaec-2221-4877-8102-159b780cdb7e) |
| App Running in Container | ![App Running](https://github.com/user-attachments/assets/6c7605b1-5bd4-4174-ab22-e921c5d83c4c) |
| MySQL Migration Success | ![DB Success](https://github.com/user-attachments/assets/616a519f-5b2b-43c6-879d-91a69501d980) |
| Image Push to ECR | ![ECR Push](https://github.com/user-attachments/assets/367d0e40-7965-4d52-b18a-7204f476dbdc) |

---

## 🧠 Key Learnings
- Hands-on experience with Docker image creation, container management, and networking.
- Integrating AWS ECR with Docker workflows.
- Understanding containerized architecture for scalable cloud apps.
- Practical migration from monolithic EC2 to containerized environments.

---

### 📍 Next Step
Deploy the Dockerized web application on **AWS Elastic Beanstalk** and integrate **Amazon RDS** for managed database hosting.

---

© 2025 Maureen Osaghae | AWS Cloud & DevOps Engineer  
