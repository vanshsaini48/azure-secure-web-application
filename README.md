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


## Architecture

The following diagram shows the architecture of the Azure Secure Web Application.

![Azure Secure Web Application Architecture](screenshots/architecture.png)


## Deployment

### Step 1 — Create Virtual Network

Create the Azure Virtual Network and configure the required address space and subnet.

Detailed configuration: [VNet.md](VNet.md)

![Azure Virtual Network](screenshots/vnet.png)
![Azure Virtual Network](screenshots/vnet1.png)
![Azure Virtual Network](screenshots/vnet2.png)
![Azure Virtual Network](screenshots/vnet3.png)
![Azure Virtual Network](screenshots/vnet4.png)

---

### Step 2 — Create Virtual Machine

Create an Ubuntu virtual machine inside the configured network and subnet.

Detailed configuration: [Virtual_Machine.md](Virtual_Machine.md)

![Azure Virtual Machine](screenshots/virtual-machine.png)
![Azure Virtual Machine](screenshots/virtual-machine1.png)
![Azure Virtual Machine](screenshots/virtual-machine2.png)
![Azure Virtual Machine](screenshots/virtual-machine3.png)
![Azure Virtual Machine](screenshots/virtual-machine4.png)
![Azure Virtual Machine](screenshots/virtual-machine5.png)
![Azure Virtual Machine](screenshots/virtual-machine6.png)
![Azure Virtual Machine](screenshots/virtual-machine7.png)
![Azure Virtual Machine](screenshots/virtual-machine8.png)

---

### Step 3 — Connect Using Azure Bastion

Configure Azure Bastion to connect securely to the private virtual machine.

Detailed configuration: [Connect_Bastion.md](Connect_Bastion.md)

![Azure Bastion](screenshots/bastion.png)
![Azure Bastion](screenshots/bastion1.png)
![Azure Bastion](screenshots/bastion2.png)
![Azure Bastion](screenshots/bastion3.png)
![Azure Bastion](screenshots/bastion4.png)


---

### Step 4 — Install Nginx

Install Nginx on the Ubuntu virtual machine and verify that the web server is running.

Detailed configuration: [Install_Nginx.md](Install_Nginx.md)

![Nginx Installation](screenshots/nginx-installation.png)
![Nginx Installation](screenshots/nginx-installation1.png)
![Nginx Installation](screenshots/nginx-installation2.png)
![Nginx Installation](screenshots/nginx-installation3.png)
![Nginx Installation](screenshots/nginx-installation4.png)
![Nginx Installation](screenshots/nginx-installation5.png)

---

### Step 5 — Create HTML Web Page

Create and configure the HTML page that will be served by Nginx.

Detailed configuration: [Create_HTML_Nginx.md](Create_HTML_Nginx.md)

![Web Application](screenshots/web-application.png)

---

### Step 6 — Configure Azure Firewall

Configure Azure Firewall and DNAT to control and publish access to the web application hosted on the private VM.

Detailed configuration: [Configure_Firewall.md](Configure_Firewall.md)

![Azure Firewall](screensots/firewall.png)
![Azure Firewall](screensots/firewall1.png)
![Azure Firewall](screensots/firewall2.png)
![Azure Firewall](screensots/firewall3.png)
![Azure Firewall](screensots/firewall4.png)
![Azure Firewall](screensots/firewall5.png)
![Azure Firewall](screensots/firewall6.png)
![Azure Firewall](screensots/firewall7.png)
![Azure Firewall](screensots/firewall8.png)
![Azure Firewall](screensots/firewall9.png)
![Azure Firewall](screensots/firewall10.png)
![Azure Firewall](screensots/firewall11.png)
![Azure Firewall](screensots/firewall12.png)
![Azure Firewall](screensots/firewall13.png)

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