# 🌐 Azure Fundamentals Hands-On Workshop
> Complete Guide for Students to Practice After the Session
> This README contains all steps covered in the workshop, including Azure navigation, resource group creation, web app hosting, and virtual machine setup.

# Prerequisites
Before starting:
- Azure Account (Free / Student Subscription)
- Stable internet connection
- Browser: Edge / Chrome
- Access Portal: https://portal.azure.com

> Workshop Web App URL:
- https://onlinedrive.onrender.com/

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

Steps:
<pre>
1. Search Resource groups
2. Click Create
3. Fill:
  - Subscription: Your subscription
  - Resource Group Name: workshop-rg
  - region: Select nearest region
4. Click Review + Create
5. Click Create
</pre>

# 📁 3. Create a Storage Account
Steps: 
<pre>
1. Search Storage accounts
2. Click Create
3. Fill:
  - Resource Group: workshop-rg
  - Storage Account Name: mystorage<yourname>
  - Region: Same as RG
  - Performance: Standard
  - Redundancy: LRS
4. Go to Advanced Tab and make anonymus access allowed (Optional if you dont want public access)
5. Click Review + Create → Create
6. Open Storage Account → Containers
7. Create new container:
  - Name: uploads
  - Public Access: Private / Blob

    
<B>Upload Files</B>
    - Open container
    - Click Upload

<B>Copy File URL</B>
    - Click file → Properties
    - Copy Blob URL
</pre>


# 🌐 4. Create a Web App (Host Your Website)
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
<pre>
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
4. GitHub Action Runs Automatically
  - Go to: GitHub → Your Repo → Actions
  - You will see the deployment pipeline running.
    - If green → Deployment succeeded.
    - If red → Something is missing (Azure will show the error).
5. Browse Your Live Website
  - After successful deployment:
  a. Go to your App Service
  b. Click Browse

Your website from GitHub is now live on Azure.
</pre>

# 🖥️ 5. Create a Virtual Machine (VM)
Steps:

<pre>
1. Search Virtual Machines
2. Click Create → Azure Virtual Machine
3. Basic Configuration
  - Resource Group: workshop-rg
  - VM Name: demo-vm-<yourname>
  - Region: Same
  - Image: Ubuntu 22.04 LTS
  - Size: B1s (Free-tier eligible)
  - Authentication:
    - Username: azureuser
    - Password or SSH key
  - Networking
    - Ensure SSH (22) is enabled
4. Click Review + Create
5. Create
</pre>

## Connect & Use the VM
<pre>
1. Go to VM → Connect → SSH
2. Copy the provided command:
    ssh azureuser@<public-ip>
3. Open Powershell
4. run command
</pre>

<B>Inside VM</B>
<pre>
1. Update system: sudo apt update && sudo apt upgrade -y
2. Install Nginx: sudo apt install nginx -y
</pre>

<B>Test</B>
<pre>
1. Open browser → Enter VM's Public IP
2. You should see the Nginx Welcome Page.
</pre>
