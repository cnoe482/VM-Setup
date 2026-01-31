<p align="center">
<img width="354" height="383" alt="azvm" src="https://github.com/user-attachments/assets/9603c62e-2994-4ef1-a933-93180870dab2" />
</p>

<h1>Azure Virtual Machine - Setup</h1>
This tutorial outlines the Setup and options available when setting up an Azure Virtual Machine.<br />

<h2>Environments and Technologies Used</h2>

- Web Browser
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 11 Pro

<h2>List of Prerequisites</h2>

- Microsoft Azure account
- Windows 11 Virtual Machine
- Remote Desktop Client

<h1>Step 1 - Create an Azure account</h1>

- <a href="https://azure.microsoft.com/en-us">Azure Website Link</a>
- Click **Get started with Azure**
- Click **Try Azure for free**
- Either Sign in with your existing Microsoft account or create one
- Follow prompts for creating your Azure account
- You should now be in the Azure Portal
- On Azure Portal: use the search bar
  - Type in "Subscriptions"
  - Click **Subscriptions**
- Select your subscription
- One the top you should see this message Click it
  - **Your remaining $200.00 of free credit expires in 30 days. Upgrade to keep going with your account.**
- Now on the Bottom of the page click **Upgrade to pay as you go**
  - Verify your payment if needed
  - Exit Azure Portal webpage and re-enter to apply updated subscriptiona
- Why do we have to do this?
  - Some features are only allowed with pay as you go
  - If you created a new account you will still have your $200 credit for 30 days


<img width="1909" height="846" alt="Step 1" src="https://github.com/user-attachments/assets/7a441e09-c92b-4dbd-8d46-3588fa6433b7" />

<img width="1902" height="843" alt="step 1-2" src="https://github.com/user-attachments/assets/7afec56d-2a17-44de-9bb2-23b995235e8c" />

<img width="1906" height="941" alt="step 1-3" src="https://github.com/user-attachments/assets/8aae662c-2c2a-4361-bd7e-1ec671b608ba" />

<img width="1881" height="333" alt="step1-4" src="https://github.com/user-attachments/assets/a0570ca4-d9ed-4cc0-8aaa-421fefd5230d" />

<img width="1471" height="807" alt="step1-5" src="https://github.com/user-attachments/assets/406a8338-f952-4875-8299-9364f2b91d31" />

<img width="857" height="947" alt="step1-6" src="https://github.com/user-attachments/assets/82f3474a-3b17-4983-b339-b2101d5c6668" />

<h1>Step 2 - Resource Group</h1>


Explanation: A Resource Group is a container that holds resources for Azure projects. This makes it easier to organize, manage, or delete these resources. Projects must have a resource group to create and manage its services.

- On Azure Portal: use the search bar
  - Type in "Resource Group"
  - Click **Resource Groups**
- On the Resource Group Page
  - Click **Create**
  - Select your subscription (Default for a new account will be "Azure Subscription 1")
  - Name your Resource Group
  - Select a region. Recommend staying in your country for lower latency
    - Region will determine where the server that host your resource group will be
  - Click Review + Create
  - Confirm Settings
  - Click Create
- View Resource Group
  - Wait a moment and click refresh
  - You should see your Resource Group Now
  - Click your Resource group
  - Here you can view the Resources in your group

<img width="842" height="675" alt="Step 2" src="https://github.com/user-attachments/assets/8c51dd0e-35cd-478e-876e-e4567ed17021" />

<img width="1902" height="942" alt="Step 2-1" src="https://github.com/user-attachments/assets/e03c0992-6f4c-4c3e-b0c8-3c16be912a37" />

<img width="948" height="949" alt="Step 2-2" src="https://github.com/user-attachments/assets/3a967b51-cb04-4b7e-97f9-cc4b753d8fdd" />

<img width="674" height="909" alt="Step 2-3" src="https://github.com/user-attachments/assets/5fa79e45-1e65-438e-8f82-2ab47564bcb5" />

<img width="1463" height="776" alt="Step 2-4" src="https://github.com/user-attachments/assets/45af6cbb-d88f-4755-8f2a-16b15f8d3986" />

<img width="1325" height="833" alt="Step 2-5" src="https://github.com/user-attachments/assets/855251b7-2188-4ade-b986-0fdfdaa4baa6" />

<h1>Step 3 - Virtual Machine (VM) Setup</h1>

Explanation: A Virtual Machine (VM) is a virtual computer that runs an operating system on a remote server, using assigned CPU, memory, and storage resources from said server.

**This will cover Basic configuration for VM creation**

- On Azure Portal: use the search bar
  - Type in "Virtual Machines"
  - Click **Virtual Machine**
- Click **Create**
  - Click **Virtual Machine**
- The Right Side of this page will show you the cost for running your VM nonstop for a month
- Select your Subscription
- Resource Group: Select the previously created one
- Virtual Machine name: Enter your name for the VM
- Choose Region: Select the same region as the Resource Group
- Availabilty Option: How the VM will be hosted
  - Avaialalbity Zone: Select a zone within a region for where you VM will be hosted
  - VM Scale Set: VM will be hosted acorss multiple zones and fault domains
      - Fault Domains are points of failure for server racks
      - Requires extra setup
  - Availability Set: Axure will automatically distribute VM acorss zones and fault domains
      - Requires extra setup
- If Zone options → Avaialalbity Zone: Self Selected or Azure-Selected
  - Regions are broken into smaller sections known as availablity zones
  - Self-Selected: will allow you to select your Availablity Zone
  - Azure-Selected: Azure will select what it believes is optimal
- If Zone options → Avaialalbity Zone:
- Choose Security Type: Trusted Launch vs Standard
- Standard: Provides default Azure security features without advanced boot protections.
- Trusted Launch: Enables Secure Boot and virtual TPM (vTPM) for enhanced security.
    - Secure Boot ensures that only trusted, digitally signed software is allowed to run on computer startup.
    - Trusted Platform Module (TPM) stores and manages encryption keys to help secure sensitive data.
- Choose Image: What Operating System you will be using
  - Ubuntu is Linux
  - Windows 11 pro is standard windows
  - Windows Server 2025 is a windows server
- Choose VM Archiecture: Type of CPU
  - ARM64: Energy-efficient CPU architecture commonly used in mobile devices
  - x64: Traditional CPU architecture used in most desktops, servers
- Size: How many CPU cores and how much Ram VM will have
  - Azure will automatically generate the standard for your selected Image
  - Click the drop down and click **See all sizes** if you want to change this
- Enter a Username
- Enter a Password
- Public inbound ports
  - None: will block all trafic by default
  - Allow Selected Ports: Allows you to select port that will be used for inbound traffic
- Agree to Licensing Agreement
- Click **Review + Create**
- Review your options then Click **Create**
- Wait while VM is Deploying
- When Deployment is finished Click **Go to resource**
- Now you should be able to see a breakdown of your VM 

<img width="609" height="725" alt="step3" src="https://github.com/user-attachments/assets/e0747861-fe56-415a-a429-b4af43126e5a" />

<img width="1907" height="907" alt="step3-2" src="https://github.com/user-attachments/assets/eec0911f-d60f-493f-a229-4c45763c013d" />

<img width="1906" height="727" alt="step3-3" src="https://github.com/user-attachments/assets/ee0e25d6-9802-4fd5-a729-79f73fc832bb" />

<img width="444" height="827" alt="step3-4" src="https://github.com/user-attachments/assets/d31f1db1-f45a-458e-9673-60bb6e4b62c2" />

<img width="914" height="866" alt="step3-5" src="https://github.com/user-attachments/assets/a6377b02-7260-4b8c-a71f-a46410855547" />

<img width="697" height="531" alt="step3-6" src="https://github.com/user-attachments/assets/69ab7b7d-c411-44a2-b097-d9817f965329" />

<img width="1909" height="927" alt="step3-7" src="https://github.com/user-attachments/assets/b87538f9-9e1a-49b4-a40e-70f59b9eb2c4" />

<img width="751" height="397" alt="step3-8" src="https://github.com/user-attachments/assets/5fdba343-4c17-4aba-b395-40936fbe0733" />

<img width="1892" height="919" alt="step3-9" src="https://github.com/user-attachments/assets/e6123f5e-7039-4d58-8d20-8baa15ebd241" />

<h1>Step 4 - Accessing your VM</h1>

- Now if you are on MAC Follow these steps
  - Access the MAC app store
  - Download **Microsoft Remote Desktop**
  - Open the newly downloaded software
- On windows follow these steps
  - On windows search bar type "Remote desktop connection"
  - Click **Remote Desktop Connection** (RDC)
- Now pull up your VM overview
  - Find your public IP address
- Now on RDC for Computer fill in the Public IP for your VM
- Click **Show Options**
  - Fill in Username with what you used for your VM
  - Click **Connect**
- A pop up asking for a password should appear
  - Use the password you used when creating your VM
- Another pop up will appear asking if you want to connect click **Yes**
  
<img width="773" height="780" alt="Step4" src="https://github.com/user-attachments/assets/e5a7474d-bdd0-4326-aeb2-3025006110d4" />

<img width="1904" height="912" alt="step4-1" src="https://github.com/user-attachments/assets/14eeca24-635c-4cb1-b91b-9623b650dc5e" />

<img width="391" height="398" alt="step4-2" src="https://github.com/user-attachments/assets/22becfa2-90c5-48bd-80ff-47785b07676b" />

<h1>Step 5 -Congradulations</h1>

- You have created and accessed your new Virtual Machine
- Follow the setup options and enjoy
  
<img width="1914" height="1075" alt="Step5" src="https://github.com/user-attachments/assets/a904eaf9-2f17-437a-a545-8daa5877197d" />

