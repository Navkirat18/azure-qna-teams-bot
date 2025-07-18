# Azure QnA Teams Bot

This project is a **secure, serverless Question-and-Answer (QnA) bot** integrated with **Microsoft Teams**, built using:

- **Azure Language Services (QnA)**
- **Azure AI Search**
- **Azure Blob Storage**
- **Azure Application Gateway**
- **Private Endpoints**
- **Microsoft Teams**

---

## 🔐 Project Goals

- Fully secure deployment — no public access to backend services
- Private access via **Application Gateway + Private Endpoints**
- Integrated with **Teams** for natural chat experience
- Uses **Azure Cognitive Services** for language understanding

---

## ⚙️ Architecture Overview

[Teams]
|
v
[Azure Bot Framework]
|
v
[Application Gateway (WAF)]
|
v
[Private Endpoint]
|
v
[Azure App Service / Function App]
|
+--> [Azure Language Resource]
|
+--> [Azure AI Search]
