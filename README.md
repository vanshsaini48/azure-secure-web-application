# Azure Secure Web Application

A network-segmented web application deployed on Microsoft Azure using Azure Virtual Network, Azure Firewall, Azure Bastion, Network Security Groups, and a private Linux virtual machine running Nginx.

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

## Security Validation

The project will validate:

- Direct access to the private VM
- Authorized access through Azure Firewall
- Unauthorized source IP access
- HTTP traffic blocked through NSG
- SSH access restrictions
- Application availability through the intended network path

## Project Structure

azure-secure-web-application/
├── architecture/
├── web-app/
├── scripts/
├── firewall/
├── networking/
├── bastion/
├── screenshots/
├── .gitignore
└── README.md

## Future Improvements

- HTTPS/TLS
- Azure Application Gateway / WAF
- Azure Monitor
- Log Analytics
- Microsoft Defender for Cloud
- Azure Key Vault
- Managed Identity
- Terraform

