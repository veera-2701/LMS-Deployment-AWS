# LMS Application Deployment on AWS

A full-stack Learning Management System (LMS) deployed on AWS using Docker containers. This project demonstrates application deployment, containerization, cloud infrastructure management, and DevOps practices using ReactJS, NodeJS, PostgreSQL, Docker, and AWS EC2.

---

## Architecture

```text
                Internet
                    │
                    ▼
                Nginx
                    │
                    ▼
          React Frontend (Port 80)
                    │
                    ▼
         NodeJS Backend (Port 8080)
                    │
                    ▼
       PostgreSQL Database (5432)
```

---

## Technologies Used

### Frontend

* ReactJS
* Vite

### Backend

* NodeJS
* ExpressJS

### Database

* PostgreSQL
* Prisma ORM

### DevOps Tools

* Docker
* Docker Compose

### Cloud Services

* AWS EC2
* Security Groups

---

## AWS Services Used

* Amazon EC2
* Security Groups
* Ubuntu Linux

---

## Container Information

| Container | Purpose           | Port |
| --------- | ----------------- | ---- |
| Frontend  | React Application | 80   |
| Backend   | NodeJS API        | 8080 |
| Database  | PostgreSQL        | 5432 |

---

## Deployment Steps

### 1. Launch EC2 Instance

* Ubuntu Server
* t3.large
* 20 GB Storage

### 2. Install Docker

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
```

### 3. Run PostgreSQL Container

```bash
docker run -dt \
--name db \
-e POSTGRES_PASSWORD=password123 \
-p 5432:5432 \
postgres
```

### 4. Deploy Backend Container

```bash
docker run -dt \
--name backend \
-v /project:/mnt/lms \
-p 8080:8080 \
ubuntu
```

### 5. Deploy Frontend Container

```bash
docker run -dt \
--name frontend \
-v /project:/mnt/lms \
-p 80:80 \
ubuntu
```

---

## Security Group Configuration

| Port | Purpose              |
| ---- | -------------------- |
| 22   | SSH Access           |
| 80   | Frontend Application |
| 8080 | Backend API          |
| 5432 | PostgreSQL Database  |

---

## Application Verification

Frontend:

```text
http://<public-ip>
```

Backend API:

```text
http://<public-ip>:8080/api
```

---

## Screenshots

### Application Home Page

(Add Screenshot)

### Login Page

(Add Screenshot)

### Dashboard

(Add Screenshot)

### Docker Containers

(Add Screenshot)

---

## Challenges Faced

* PostgreSQL connectivity issues
* Docker networking configuration
* Environment variable management
* Prisma client compatibility issues
* Frontend to backend communication troubleshooting

---

## Future Enhancements

* Jenkins CI/CD Pipeline
* SonarQube Integration
* Nexus Repository Integration
* Terraform Infrastructure Automation
* Kubernetes Deployment
* AWS CloudFront Integration
* AWS WAF Protection

---

## Author

**Veera Babu Paidikondala**

GitHub: https://github.com/veera-2701

LinkedIn: https://www.linkedin.com/in/veera-babu-3264b9214/
