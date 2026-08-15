# Azure Secure Web Application

A network-segmented web application deployed on **Microsoft Azure** using Azure Virtual Network, Azure Firewall, Azure Bastion, Network Security Groups, and a private Linux virtual machine running Nginx.

## Project Objectives

- Deploy a web application on a private Azure VM
- Remove direct Internet exposure from the application VM
- Control inbound traffic using Azure Firewall
- Use DNAT to securely publish the web application
- Use Azure Bastion for administrative access
- Restrict network traffic using NSGs
- Validate authorized and unauthorized traffic paths

## Azure Components

- Azure Resource Group
- Azure Virtual Network
- Web Application Subnet
- Azure Firewall
- Azure Bastion
- Network Security Group
- Ubuntu VM
- Nginx

## Security Controls

- Private VM without a public IP
- Azure Firewall for inbound traffic control
- DNAT for controlled application publishing
- NSG rules for network-level traffic filtering
- Azure Bastion for administrative access
- Restricted source IP access

## Deployment

### Step 1 — Create Virtual Network

Create the Azure Virtual Network and configure the required address space and subnet.

Detailed configuration: [VNet.md](VNet.md)

![Azure Virtual Network](ss/vnet.png)

---

### Step 2 — Create Virtual Machine

Create an Ubuntu virtual machine inside the configured network and subnet.

Detailed configuration: [Virtual_Machine.md](Virtual_Machine.md)

![Azure Virtual Machine](ss/virtual-machine.png)

---

### Step 3 — Connect Using Azure Bastion

Configure Azure Bastion to connect securely to the private virtual machine.

Detailed configuration: [Connect_Bastion.md](Connect_Bastion.md)

![Azure Bastion](ss/bastion.png)

---

### Step 4 — Install Nginx

Install Nginx on the Ubuntu virtual machine and verify that the web server is running.

Detailed configuration: [Install_Nginx.md](Install_Nginx.md)

![Nginx Installation](ss/nginx-installation.png)

---

### Step 5 — Create HTML Web Page

Create and configure the HTML page that will be served by Nginx.

Detailed configuration: [Create_HTML_Nginx.md](Create_HTML_Nginx.md)

![Web Application](ss/web-application.png)

---

### Step 6 — Configure Azure Firewall

Configure Azure Firewall and DNAT to control and publish access to the web application hosted on the private VM.

Detailed configuration: [Configure_Firewall.md](Configure_Firewall.md)

![Azure Firewall](ss/firewall.png)

---

## Security Validation

The project validates:

- Direct access to the private VM
- Authorized access through Azure Firewall
- Unauthorized source IP access
- HTTP traffic blocked through NSG
- SSH access restrictions
- Application availability through the intended network path

## Project Structure

```text
azure-secure-web-application/
│
├── .gitignore
├── README.md
├── VNet.md
├── Virtual_Machine.md
├── Connect_Bastion.md
├── Install_Nginx.md
├── Create_HTML_Nginx.md
├── Configure_Firewall.md
│
└── screenshots/
    ├── vnet.png
    ├── virtual-machine.png
    ├── bastion.png
    ├── nginx-installation.png
    ├── web-application.png
    └── firewall.png