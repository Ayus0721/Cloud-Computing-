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

