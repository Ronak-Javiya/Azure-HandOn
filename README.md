# 🌐 Azure Fundamentals Hands-On Workshop
> Complete Guide for Students to Practice After the Session
> This README contains all steps covered in the workshop, including Azure navigation, resource group creation, web app hosting, and virtual machine setup.

# Prerequisites
Before starting:
- Azure Account (Free / Student Subscription)
- Stable internet connection
- Browser: Edge / Chrome
- Access Portal: https://portal.azure.com

# 🧭 1. Azure Portal Navigation
Azure Portal main sections:
1. Home — Overview of commonly used services
2. Search Bar — Quickly find any service (recommended)
3. Resource Groups — Organize all Azure resources
4. Notifications — Shows deployment progress
5. Cloud Shell — Terminal (Bash / PowerShell) in browser
- Tip: Always use the search bar (Example: “VM”, “App Services”, “Storage”).

# 📦 2. Create a Resource Group
A Resource Group (RG) is a container for all Azure resources in your project.

Steps
1. Search Resource groups
2. Click Create
3. Fill:
  - Subscription: Your subscription
  - Resource Group Name: workshop-rg
  - region: Select nearest region
4. Click Review + Create
5. Click Create

# 🌐 3. Create a Web App (Host Your Website)
Azure App Service lets you host static or dynamic websites.

Steps
<pre>
1. Search App Services
2. Click Create
3. Fill:
  - Resource Group: workshop-rg
  - Name: my-webapp-demo-<yourname>
  - Publish: Code
  - Runtime Stack: Node 18 / Python 3.10
  - OS: Linux
  - Plan: Free (F1)
4. Click Review + Create → Create
5. After deployment → Click Go to Resource
6. Click Browse to view the default page
</pre>

## Deploy Your Web App Using Github

1. Create a GitHub Repository
2. Add Your Website Files
3. Connect GitHub to Azure App Service
- Go to your App Service in Azure
- Left menu → Deployment Center
- Choose:
  - Source: GitHub
  - Repository: your repo
  - Branch: main
  - Build Provider: GitHub Actions
- Click Save / Finish
- Azure automatically generates a workflow file in your repo: .github/workflows/azure-webapps.yml
- This file builds and deploys your website every time you push a commit.

