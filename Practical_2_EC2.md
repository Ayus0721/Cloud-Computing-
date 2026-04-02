# Create EC2
## Step 1: Launch EC2 Instance

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

## Step 2: Connect to EC2

### Using SSH:
1. Open terminal
2. Run:
ssh -i your-key.pem ec2-user@your-public-ip

### Using Browser:
- Click "Connect" → EC2 Instance Connect

# Step 3: Security Groups

### Allow:
- SSH (22) → Your IP
- HTTP (80) → Anywhere (0.0.0.0/0)

### Note:
Security groups act as firewall.

## Step 4: Storage (EBS)

### Default:
- 8GB root volume

### Add Volume:
1. Go to Volumes
2. Create new volume
3. Attach to EC2

### Mount:
Use Linux commands to mount the disk.

## Step 5: Elastic IP

### Steps:
1. Allocate Elastic IP
2. Associate with EC2

### Benefit:
Static public IP address

## Step 6: Cleanup

1. Stop or terminate EC2
2. Release Elastic IP
3. Delete unused volumes

✅ Avoid unnecessary charges
