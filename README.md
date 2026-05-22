# aws-security-group-lab
A hands-on AWS lab to create and configure a Security Group for EC2 instances, applying the principle of least privilege.
---

## 📋 Description

This practical AWS lab guides you step by step to:

- 🛡️ Create a **Security Group** (virtual firewall) for your EC2 instances
- ⚙️ Configure precise **inbound/outbound rules**
- ✅ Apply **security best practices** (principle of least privilege)

Ideal for beginner cloud administrators and engineers, this lab teaches you how to protect your AWS resources against unauthorized access.

---

## 🏷️ Keywords

`AWS Security Group` · `EC2 Security Rules` · `Network Security` · `Inbound Outbound Rules` · `EC2 Server Protection` · `EC2 Access Management`

---

## ❓ Context: Why This Lab?

AWS Security Groups are essential for:

- **Controlling traffic** to your instances (allow only what's necessary)
- **Preventing attacks** (open ports = potential risks)
- **Isolating environments** (e.g., one SG for databases, another for web servers)

> ⚠️ **Common mistake:** Overly permissive rules (`0.0.0.0/0` on all ports) can expose your resources to cyberattacks.

---

## 🚀 Instructions (Step-by-Step)

### Step 1 — Create the Security Group

1. Go to the **EC2 Console** → **Security Groups** → **Create Security Group**
2. Name it (e.g., `TP-Web-Server-SG`)
3. Add a clear description (e.g., *"Allows HTTP/HTTPS/SSH from my IP"*)
4. Select the **default VPC** (or an existing VPC)

---

### Step 2 — Configure Inbound Rules (Incoming Traffic)

| Rule | Protocol | Port | Source |
|------|----------|------|--------|
| SSH  | TCP | 22 | Your public IP (or a specific IP range) |
| HTTP | TCP | 80 | `0.0.0.0/0` (allow all web traffic) |
| HTTPS | TCP | 443 | `0.0.0.0/0` |

---

### Step 3 — Configure Outbound Rules (Outgoing Traffic)

- By default, AWS **allows all outgoing traffic**.
- To harden security, **limit to necessary ports only** (e.g., HTTP/HTTPS only).

---

### Step 4 — Associate with an EC2 Instance

1. Go to **Instances** → Select your instance
2. Click **Actions** → **Security** → **Change Security Groups**
3. Add your new group (`TP-Web-Server-SG`)

---

### Step 5 — Test the Rules

- Try connecting via SSH to verify port 22 is accessible from your IP only
- Open a browser and navigate to your instance's public IP to test HTTP/HTTPS access
- Verify that unauthorized ports are blocked

---

## 🎓 What You Learned

- ✅ Create a Security Group and configure precise rules
- ✅ Apply the **principle of least privilege** (don't open all ports)
- ✅ Associate a Security Group with an EC2 instance
- ✅ Test connectivity to validate the rules

---

## 📚 Prerequisites

- An active AWS account
- Basic knowledge of the AWS Console
- An EC2 instance running (or ready to launch one)

---

## 🔗 Useful Resources

- [AWS Security Groups Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html)
- [AWS EC2 Console](https://console.aws.amazon.com/ec2/)
- [AWS Well-Architected Framework – Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)

---

## 📄 License

This lab is for educational purposes. Feel free to use and adapt it for your own learning or teaching.
