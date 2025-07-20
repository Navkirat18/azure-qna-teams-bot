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

##🔧 Azure Services Used
Service	Purpose
Azure AI Language	Used for QnA Maker-style question-answering (language understanding)
Azure AI Search	Indexes documents from qna-docs/ folder for semantic search
Azure Blob Storage	Stores uploaded documents for knowledge base
Azure Web App Bot / Bot Channels Registration	Hosts and manages the Teams-integrated bot
Azure Private Endpoints	Restricts public access, enabling only VNet-bound secure communication
Azure Virtual Network (VNet)	Ensures all resources are deployed in a secure virtual network
Azure Application Gateway	Provides secure frontend access with routing and TLS termination
Microsoft Teams	Bot is deployed and tested in Teams via App ID registration

✅ Step-by-Step Setup
1. Resource Group & VNet
Create QnABotRG

VNet: QnABotVNet with subnets:

PrivateEndpointSubnet

AppGatewaySubnet

BotSubnet (optional)

2. Blob Storage
Container name: qna-docs

Upload .pdf, .docx, .txt, etc.

3. Azure AI Search
Create service

Define index from Blob storage

Load and test data

4. Azure AI Language (Language Studio)
Resource: QNA-BOT-LANG-05

Author a QnA project

Connect to Azure AI Search

Publish project

5. Bot Registration
Register bot in Azure

Configure Microsoft Teams as a channel

Get App ID and Client Secret

6. Create Private Endpoint
Service: QNA-BOT-LANG-05

Subnet: PrivateEndpointSubnet

DNS Zone: privatelink.cognitiveservices.azure.com

7. DNS Configuration
Private DNS Zone linked with VNet

Automatically resolves qna-bot-lang-05.privatelink.cognitiveservices.azure.com to Private IP

8. App Gateway (optional but recommended)
Deploy in AppGatewaySubnet

Configure front-end for bot service

Enable TLS, WAF policies, routing rules

9. Test Bot in Teams
Use Teams App Studio or Azure Bot registration

Provide Bot App ID

Test conversations
