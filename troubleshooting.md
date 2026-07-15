# Troubleshooting: Unable to Establish SSH Connection to AWS EC2

## Problem Statement
Administrators encounter a "Connection timeout" or "Connection refused" error message when attempting to initiate an SSH session into an Amazon EC2 Linux instance.

## Technical Causes
This issue typically stems from misconfigured network access lists, closed daemon ports, or a stopped virtual machine instance.

## Diagnostic and Resolution Steps

### Step 1: Validate Instance State
1. Open the AWS Management Console and navigate to the EC2 Dashboard.
2. Click "Instances (running)".
3. Locate your target instance and verify that the Instance state is explicitly marked as "Running". 
   * If the instance is stopped, select the instance, click "Instance state", and select "Start instance".

### Step 2: Audit Security Group Inbound Rules
1. In the EC2 instance description dashboard, select the Security tab for the target instance.
2. Click the active Inbound security groups link.
3. Verify that an inbound rule exists allowing traffic under the following parameters:
   * Type: SSH
   * Protocol: TCP
   * Port Range: 22
   * Source: Your current public IP address (e.g., YOUR_IP/32) or the company VPN CIDR block.
4. If the rule is missing, click "Edit inbound rules", append the rule parameters defined above, and click "Save rules".

### Step 3: Test Connection Remote State
1. Return to your local terminal shell interface.
2. Execute the SSH connection string again using your explicit private key file (.pem):
   ```bash
   ssh -i "your-key.pem" ec2-user@your-instance-public-dns.compute-1.amazonaws.com