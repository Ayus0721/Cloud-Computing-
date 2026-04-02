# Create VPC
## Step 1: Create a VPC

### Steps:
1. Go to AWS Console
2. Navigate to VPC Dashboard
3. Click "Create VPC"

### Configuration:
- Name: my-vpc
- CIDR Block: 10.0.0.0/16
- Tenancy: Default

### Result:
Your VPC is created successfully.

---

## Step 2: Create Subnets

### Public Subnet:
- CIDR: 10.0.1.0/24
- AZ: ap-south-1a

### Private Subnet:
- CIDR: 10.0.2.0/24
- AZ: ap-south-1b

### Tip:
Enable auto-assign public IP for public subnet.

---

## Step 3: Create Internet Gateway

1. Go to Internet Gateways
2. Click "Create"
3. Attach to your VPC

This allows internet access for public resources.

---

## Step 4: Configure Route Tables

### Public Route Table:
- Add route: 0.0.0.0/0 → Internet Gateway

### Associate:
- Link with Public Subnet

---

## Step 5: NAT Gateway

1. Create NAT Gateway in Public Subnet
2. Allocate Elastic IP

### Private Route Table:
- Route: 0.0.0.0/0 → NAT Gateway

---

## Step 6: Security

### Security Groups:
- Allow HTTP (80)
- Allow SSH (22)

### NACL:
- Allow inbound/outbound traffic as needed

---

## Step 7: Testing

1. Launch EC2 in Public Subnet → should have internet
2. Launch EC2 in Private Subnet → no direct internet
3. Verify NAT Gateway works

✅ Setup Complete!
