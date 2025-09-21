# 🌩️ Cloud-Enabled Deployment with AWS & GCP

This project shows how to build and deploy a **microservices-based system** using **Spring Boot, React, and Docker** on **AWS and GCP**.  
It includes steps to **develop, containerize, and deploy** backend services and a frontend app with support for both **cloud** and **local databases**.

---

## 👤 Author
| Name           | Student ID | Email                  | GitHub             |
|----------------|------------|------------------------|--------------------|
| Gavesh Prabath | 2301682047 | gajimax12345@gmail.com | [GitHub Profile](https://github.com/gaaji12345) |

---

## 📂 Repository Structure
- **course-service** → Spring Boot + MySQL (AWS & GCP deployment)
- **student-service** → Spring Boot + MongoDB
- **media-service** → Spring Boot + Local file storage (extensible to S3/MinIO)
- **frontend-app** → React + TypeScript

---

## ⚙️ Backend Services

### 1. Course Service
- **Entity:** `Course(id, name, duration)`
- **REST Endpoints:**
   - `GET /courses`
   - `GET /courses/{id}`
   - `POST /courses`
   - `DELETE /courses/{id}`
- **Port:** `8081`
- **Requires:** MySQL

---

### 2. Student Service
- **Document:** `Student(registrationNumber, fullName, address, contact, email)`
- **REST Endpoints:**
   - `GET /students`
   - `GET /students/{id}`
   - `POST /students`
   - `DELETE /students/{id}`
- **Port:** `8082`
- **Requires:** MongoDB

---

### 3. Media Service
- **Resource:** File storage
- **REST Endpoints:**
   - `POST /files` → upload (multipart/form-data)
   - `GET /files` → list all
   - `GET /files/{id}` → retrieve file
   - `DELETE /files/{id}` → delete file
- **Port:** `8083`
- **Storage:** `./data/media` (configurable with `MEDIA_STORAGE_DIR`)

---

## 📥 Clone the Project
```bash
git clone https://github.com/gaaji12345/Enterprise-Cloud-Architecture.git
```

## 🎨 Frontend Application
- **Stack:** React, TypeScript, Material UI, Axios, Vite
- **Features:** Courses, Students, Media Management
- **Scripts:**
  ```bash
  npm run dev       # Start development server
  npm run build     # Build production-ready bundle
  npm run preview   # Preview build output
  ```

---

## 🛠️ Development Environment

### 🔨 Build Instructions
**Backend Services:**
```bash
mvn -q -e -DskipTests package
```

**Frontend Application:**
```bash
cd frontend-app
npm install
npm run dev
```

---

### 🗄️ Local Database Setup (Docker)

**Start MySQL**
```bash
docker run -d --name mysql   -v mysql-data:/var/lib/mysql   -e MYSQL_ROOT_PASSWORD=mysql   -p 15000:3306 mysql:lts
```

**Start MongoDB**
```bash
docker run -d --name mongo   -v mongo-data:/data/db   -e MONGO_INITDB_ROOT_USERNAME=root   -e MONGO_INITDB_ROOT_PASSWORD=mongo   -p 16000:27017 mongo:latest
```

✅ Data is persisted via Docker volumes: `mysql-data`, `mongo-data`

---

## 🚀 Deployment
- **Containerized with Docker** for portability
- Supports both **Cloud-managed** and **Self-hosted** databases
- Configurable for:
   - **AWS** → EC2 + RDS + S3
   - **GCP** → Compute Engine + Cloud SQL + Cloud Storage

(Infrastructure-as-Code templates included in the repository.)

---

## 🧰 Technology Stack
- **Backend:** Spring Boot, Maven
- **Frontend:** React, TypeScript, Vite, Material UI
- **Databases:** MySQL, MongoDB
- **DevOps:** Docker
- **Cloud:** AWS, GCP

---

## 🎥 Demo
👉 Watch the demo video (https://drive.google.com/file/d/1vi24J8zWvE6x3-8dCL7FVSSX4xb6t5TI/view?usp=drive_link)

---

## 📜 License
This project is licensed under the **MIT License** – see the [LICENSE](./LICENSE) file for details.
