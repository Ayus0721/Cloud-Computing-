# Create EC2
## Step Launch EC2 Instance

### Steps:
1. Go to AWS Console
2. Navigate to EC2 Dashboard
3. Click "Launch Instance"

### Configuration:
- Name: my-ec2-instance
- AMI: Amazon Linux 2
- Instance Type: t2.micro (Free tier)
- Key Pair: Create or select existing
- Network: Default VPC

### Result:
Your EC2 instance is launched successfully.

## Connect to EC2

### Using SSH:
1. Open terminal
2. Run:
ssh -i your-key.ppk ec2-user@your-public-ip

### Note:
Security groups act as firewall.

## Storage (EBS)

### Default:
- 8GB root volume

## Cleanup

1. Stop or terminate EC2
2. Release Elastic IP
3. Delete unused volumes

✅ Avoid unnecessary charges

<img width="1918" height="1078" alt="Instances" src="https://github.com/user-attachments/assets/50bb3003-3361-4502-9d09-7fcab431b10a" />
<img width="1918" height="1078" alt="Instances2" src="https://github.com/user-attachments/assets/7f2dae23-9404-49bd-ae17-cd7250ed087a" />
<img width="1918" height="1078" alt="Instances3" src="https://github.com/user-attachments/assets/32114803-2ef8-4b58-9c42-37211ef5f68e" />
<img width="1918" height="1078" alt="Vm" src="https://github.com/user-attachments/assets/01fe4a77-ec49-40b0-a59c-9e9446189ea5" />
<img width="1918" height="1078" alt="Putty" src="https://github.com/user-attachments/assets/2fcf9a7e-24b8-44f2-b65d-8198f4791d10" />


