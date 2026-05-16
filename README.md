# 🚀 Azure Capstone Project (Flask + Azure Storage + Application Gateway + Traffic Manager)

## 📌 Project Overview

In this project, I built and deployed a cloud-based web application on **Microsoft Azure** using multiple services:

- Flask Web Application
- Azure Virtual Machines
- Azure Virtual Networks (VNets)
- VNet Peering
- Azure Blob Storage
- Application Gateway (Multi-region setup)
- Traffic Manager (Global Load Balancing)

### 🎯 Key Features
- Home page and Upload page hosted on VMs
- File upload functionality to Azure Blob Storage
- High availability using multi-region architecture
- Global traffic routing using Azure Traffic Manager

---

## 🧠 Challenges Faced

- Initially, the Flask application was not running because Flask was not installed on the VM, which caused import errors while executing `app.py`.
- Faced Python runtime issues due to missing dependencies and incorrect configuration in `config.py`.
- Resolved these issues by installing required dependencies and validating configuration before running the application successfully.

---

## 🧰 Prerequisites

- 4 Virtual Machines
- 2 Virtual Networks (VNets)
- VNet Peering
- Azure Storage Account (Blob Storage)
- 2 Application Gateways (Central US & West US)
- Traffic Manager Profile
- Flask application source code

---

## 🏗️ Architecture Overview

This architecture is designed for **high availability, scalability, and fault tolerance** across regions.

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
- VNet Peering configured between both VNets

📷 VNet Peering:

![VNet Peering](screenshots/vnet-peering.png)

---

## 🖥️ Virtual Machines Setup

### Central US Region
- VM1 → Upload Page
- VM2 → Home Page

### West US Region
- VM1 → Upload Page
- VM2 → Home Page

---

## 💾 Azure Storage Account

- Storage Type: Blob Storage
- Container Name: `upload`
- Access Level: Public/static access configured
- Static error page enabled using `error.html`

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
- Backend Pool created
- Routing rules configured

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

Same configuration as Central US region.

---

## 🌍 Traffic Manager

- Used for global traffic routing across regions
- DNS-based load balancing
- Ensures high availability and failover support

📷 Traffic Manager:

![Traffic Manager](screenshots/traffic-manager.png)

---

## 🧪 Application Deployment Steps

### 1️⃣ Update VM
```bash
sudo apt update
```

### 2️⃣ Clone Repository
```bash
git clone https://github.com/azcloudberg/azproject.git
cd azproject
```

### 3️⃣ Configure Storage
```bash
sudo nano config.py
```
(Add Storage Account Name and Access Key)

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
3. Upload a file  
4. File gets stored in Azure Blob Storage  

---

## 📷 Application Screenshots

### Home Page
![Home Page](screenshots/home-page.png)

### Upload Page
![Upload Page](screenshots/upload-page.png)

### Flask Running
![Flask App Running](screenshots/flask-app-running.png)

---

## 🎯 Final Outcome

- Multi-region deployment successfully implemented  
- High availability achieved using Traffic Manager  
- Secure file upload to Azure Blob Storage  
- Fully functional Flask-based cloud application  

---

## ✅ Project Status

✔ Successfully Completed  
✔ End-to-End Azure Deployment  
✔ Production-style architecture implemented  
