# 🚀 Azure Capstone Project (Flask + Azure Storage + Application Gateway + Traffic Manager)

## 📌 Project Overview

This project demonstrates a complete end-to-end cloud web application deployed on **Microsoft Azure** using multiple services like:

- Flask Web Application
- Azure Virtual Machines
- Azure Virtual Networks (VNets)
- VNet Peering
- Azure Blob Storage
- Application Gateway (Multi-region)
- Traffic Manager (Global Load Balancing)

The system supports:
- Home page and Upload page hosted on VMs
- File upload to Azure Blob Storage
- High availability using multi-region deployment
- Global routing using Traffic Manager

---

## 🧰 Prerequisites

- 4 Virtual Machines
- 2 Virtual Networks (VNets)
- VNet Peering
- Azure Storage Account (Blob Storage)
- 2 Application Gateways (Central US & West US)
- Traffic Manager Profile
- Flask application scripts

---

## 🏗️ Architecture Overview

The architecture is designed for **high availability, scalability, and fault tolerance**.

📷 Architecture Diagram:

![Architecture](screenshots/architecture.png)

---

## ☁️ Azure Resources Setup

### 📦 Resource Group
- Name: `capstone-project`

---

### 🌐 Virtual Networks

- VNet-1 → Central US  
- VNet-2 → West US  
- VNet Peering configured between VNet-1 and VNet-2

📷 VNet Peering:

![VNet Peering](screenshots/vnet-peering.png)

---

## 🖥️ Virtual Machines Setup

### Central US
- VM1 → Upload Page
- VM2 → Home Page

### West US
- VM1 → Upload Page
- VM2 → Home Page

---

## 💾 Azure Storage Account

- Storage Type: Blob Storage
- Container Name: `upload`
- Access Level: Configured for public/static access
- Static Error Page enabled using `error.html`

📷 Storage Account:

![Storage Account](screenshots/storage-account.png)

📷 Blob Container:

![Blob Container](screenshots/blob-container.png)

📷 Static Website:

![Static Website](screenshots/static-website.png)

---

## 🌐 Application Gateway

### 1️⃣ Central US Application Gateway

- Listener configured
- Backend Pool added
- Routing Rules configured

📷 Overview:
![AG Overview](screenshots/application-gateway-overview.png)

📷 Listener:
![AG Listener](screenshots/application-gateway-listener.png)

📷 Backend Pool:
![AG Backend Pool](screenshots/application-gateway-backend-pool.png)

📷 Routing Rule:
![AG Routing Rule](screenshots/application-gateway-routing-rule.png)

---

### 2️⃣ West US Application Gateway

(Same configuration as Central US)

---

## 🌍 Traffic Manager

- Used for global routing between regions
- DNS-based load balancing
- Ensures high availability

📷 Traffic Manager:

![Traffic Manager](screenshots/traffic-manager.png)

---

## 🧪 Application Deployment Steps

### 1️⃣ Update VM
```bash
sudo apt update
```

---

### 2️⃣ Clone Repository
```bash
git clone https://github.com/azcloudberg/azproject.git
cd azproject
```

---

### 3️⃣ Configure Storage
```bash
sudo nano config.py
```

(Add Storage Account Name + Access Key)

---

### 4️⃣ Run Application

- VM1 → Home Page  
- VM2 → Upload Page  

```bash
sudo python3 app.py
```

---

## 📤 File Upload Flow

1. Open Traffic Manager DNS  
2. Navigate to:

```
/upload
```

3. Upload file  
4. File stored in Azure Blob Storage    

---

## 📷 Application Screenshots

### Home Page
![Home Page](screenshots/home-page.png)

### Upload Page
![Upload Page](screenshots/upload-page.png)

### Flask Running
![Flask App](screenshots/flask-app-running.png)

---

## 🎯 Final Outcome

- Multi-region deployment working  
- High availability using Traffic Manager  
- Secure file upload to Azure Blob Storage  
- Fully functional Flask cloud application  

---

## ✅ Project Status

✔ Completed Successfully  
✔ End-to-end Azure Deployment  
✔ Production-style architecture implemented  
