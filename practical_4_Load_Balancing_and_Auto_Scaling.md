# Auto Scaling

## Step 1: Create Launch Template

1. Go to EC2 Dashboard
2. Click "Launch Templates" → Create

### Configuration:
- Name: my-launch-template
- AMI: Amazon Linux 2
- Instance Type: t2.micro
- Key Pair: Select existing
- Security Group:
  - Allow HTTP (80)
  - Allow SSH (22)

---

## Step 2: Create Auto Scaling Group

1. Go to Auto Scaling Groups
2. Click "Create"

### Configuration:
- Name: my-asg
- Launch Template: Select created template
- VPC: Default or custom
- Subnets: Select at least 2 AZs

### Capacity:
- Desired: 2
- Min: 1
- Max: 4

---

# Step 3: Configure Scaling Policy

## Target Tracking Policy:
- Metric: Average CPU Utilization
- Target Value: 50%

## Behavior:
- Scale out when CPU > 50%
- Scale in when CPU < 50%

---

# Step 4: Create Application Load Balancer

1. Go to EC2 → Load Balancers
2. Click "Create ALB"

## Configuration:
- Scheme: Internet-facing
- Listener: HTTP (80)
- AZs: Select multiple subnets

## Target Group:
- Type: Instances
- Health Check Path: /

---

# Step 5: Attach ASG to ALB

1. Edit Auto Scaling Group
2. Attach to Target Group

## Result:
Traffic is now distributed across instances

---

# Step 6: Testing Scaling

## Get ALB DNS:
- Open Load Balancer → Copy DNS name

## Simulate Load:
Use tools like:
- Apache Benchmark (ab)
- curl loop

Example:
while true; do curl http://<ALB-DNS>; done

## Observe:
- CPU usage increases
- New instances launched automatically

# Step 7: Cleanup

1. Delete Auto Scaling Group
2. Delete Load Balancer
3. Delete Launch Template

✅ Avoid charges
