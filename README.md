# PowerShell-VM-Orchestrator

PowerShell-VM-Orchestrator is a versatile tool designed to execute PowerShell scripts across multiple Azure Virtual Machines (VMs) within a tenant. In this implementation, it checks if the Windows Firewall allows incoming ping requests (using the ICMPv4 protocol) related to file and printer sharing on all running VMs in the Azure subscription. This project showcases automation using PowerShell and Azure Cloud Shell to streamline configuration management.

### Features
- Automates the execution of scripts across multiple Azure VMs.
- Checks to see if the Windows Firewall allows incoming ping requests (using the ICMPv4 protocol) related to file and printer sharing on all running VMs in the Azure subscription
- Utilises Azure Cloud Shell for easy and secure script deployment.
- Demonstrates the power of PowerShell for Azure resource management.


### Tasks
1. Create a Powershell Script to check the firewall rules status on the VMs.
2. Use CloudShell to execute the script on all running VMs within my subscription.

### Prerequisites
Before starting, ensure the following:
- An active Azure Subscription with running Virtual Machines.
- Permission to manage VMs in the subscription.
- Access to Azure Cloud Shell.

### How It Works in Practice
- Sets the context to the correct Azure subscription.
- Filters out non-running or non-Windows VMs.
- Runs a PowerShell script (test.ps1) on all filtered VMs concurrently using Invoke-AzVMRunCommand.
- Outputs the results for each VM with its name and the script output message.

#### Step 1 - Powershell Script




