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
<img width="1918" height="1078" alt="vpc" src="https://github.com/user-attachments/assets/6c57585d-2769-412f-b396-e87a62210246" />

---

### Result:
Your VPC is created successfully.
<img width="1918" height="1078" alt="vpc2" src="https://github.com/user-attachments/assets/adbfd768-6aa3-4199-a791-6c57865ebc61" />

---


## Step 2: Create Subnets

### Public Subnet:
- CIDR: 10.0.1.0/24
- AZ: ap-south-1a

<img width="1923" height="1074" alt="image" src="https://github.com/user-attachments/assets/cd64843f-5f70-4df3-a1c1-d8dfd3bbc025" />

### Your public subnet is created successfully.

<img width="1918" height="1078" alt="Subnet" src="https://github.com/user-attachments/assets/a9c120ff-27c8-4f6e-bed2-dcad81316757" />

---

### Private Subnet:
- CIDR: 10.0.2.0/24
- AZ: ap-south-1b

<img width="1917" height="1077" alt="Private subnet" src="https://github.com/user-attachments/assets/f8197dc8-29bd-482c-a6ea-2b45d08bc479" />


### Tip:
Enable auto-assign public IP for public subnet.

---
## Create a public EC2 instance 

<img width="1918" height="967" alt="Vpc Instance" src="https://github.com/user-attachments/assets/de3b647d-58c3-495e-b03d-37d3258ce8cd" />

## Step 3: Create Internet Gateway

1. Go to Internet Gateways
2. Click "Create"
3. Attach to your VPC

This allows internet access for public resources.

<img width="1918" height="971" alt="Igw" src="https://github.com/user-attachments/assets/1991a161-20b6-4967-9a22-75185351fc2b" />

---

## Step 4: Configure Route Tables

### Public Route Table:
- Add route: 0.0.0.0/0 → Internet Gateway

<img width="1918" height="960" alt="Route pub" src="https://github.com/user-attachments/assets/9ce9e106-a70d-4606-8721-7d42ae2969cd" />


### Associate:
- Link with Public Subnet

<img width="1918" height="966" alt="associate" src="https://github.com/user-attachments/assets/db802c06-7666-4223-9fd2-829192f4d81b" />

---

## Step 5: NAT Gateway

1. Create NAT Gateway in Public Subnet
2. Allocate Elastic IP

<img width="1918" height="968" alt="new" src="https://github.com/user-attachments/assets/5d090172-ff47-4bff-ae3d-3ccda379326f" />

<img width="1617" height="908" alt="Nat succeed" src="https://github.com/user-attachments/assets/f0191400-ff00-460c-9921-096c0735dbbb" />

---

### Private Route Table:
- Route: 0.0.0.0/0 → NAT Gateway
<img width="1918" height="957" alt="route nat" src="https://github.com/user-attachments/assets/a98c8a90-6877-4aa1-90cf-40a9cc84df20" />

---


## Step 6: Testing

1. Launch EC2 in Public Subnet → should have internet

<img width="1918" height="1078" alt="Testing" src="https://github.com/user-attachments/assets/1a14a908-669c-4013-93f1-a920627ee93c" />


2. Launch EC2 in Private Subnet → no direct internet
3. Verify NAT Gateway works

✅ Setup Complete!
