# Practical 01 - EC2 + Nginx Static Website

## 📌 Objective

- Launch EC2 instance
- Connect using SSH
- Install Nginx
- Host static website

---

## 🚀 Steps Performed

### 1. Open AWS Console
- Logged into AWS
- Opened EC2 Dashboard

### 2. Launch EC2 Instance
- Selected Ubuntu AMI
- Instance type: t2.micro
- Allowed ports:
  - SSH (22)
  - HTTP (80)

### 3. Connect using SSH

```bash
ssh -i your-key.pem ubuntu@your-public-ip
```

### 4. Install Nginx

```bash
sudo apt update -y
sudo apt install nginx -y
```

### 5. Start Nginx

```bash
sudo systemctl start nginx
```

### 6. Host Static Website

```bash
cd /var/www/html
sudo nano index.html
```

Added custom HTML page.

---

## ✅ Output

- EC2 instance launched successfully
- Nginx installed
- Website hosted and accessible via browser

---

## 📂 Detailed Steps

👉 Full detailed documentation:  
[Click Here](./README.md)

---

## 👨‍💻 Author

Sanket Pachekar
