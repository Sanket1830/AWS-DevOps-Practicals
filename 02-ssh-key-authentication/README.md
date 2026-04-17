# Practical 02 - SSH Key-Based Authentication (Passwordless Login)

## 📌 Objective

The objective of this practical is to:

- Generate SSH key pair on local system
- Create a new user on EC2 instance
- Configure SSH key-based authentication
- Enable passwordless login to the server

---

# 🛠 Services / Tools Used

- AWS EC2
- Ubuntu Linux
- SSH
- SSH Keygen
- SCP

---

# 📚 Concepts Covered

- SSH Authentication
- Public and Private Key
- Authorized Keys
- Linux User Management
- Secure Remote Access

---

# 🧭 Architecture

```text
Local Machine
    |
    | SSH (Key-based Authentication)
    v
AWS EC2 Server
    |
    | Authorized Keys
    v
New Linux User (sanket)
```

---

# 🚀 Step-by-Step Implementation

## Step 1: Generate SSH Key on Local Machine

```bash
ssh-keygen
```

- Key name: `localkey`
- Files generated:
  - `localkey` (Private Key)
  - `localkey.pub` (Public Key)

---

## Step 2: Connect to EC2 Server

```bash
ssh -i sanket.pem ubuntu@your-public-ip
```

---

## Step 3: Switch to Root User

```bash
sudo -i
```

---

## Step 4: Create New User

```bash
adduser sanket
```

(Set password when prompted)

---

## Step 5: Create .ssh Directory

```bash
mkdir /home/sanket/.ssh
```

---

## Step 6: Create authorized_keys File

```bash
touch /home/sanket/.ssh/authorized_keys
```

---

## Step 7: Copy Public Key

👉 Open `localkey.pub` in Notepad and copy full content

Then run:

```bash
nano /home/sanket/.ssh/authorized_keys
```

👉 Paste public key and save

---

## Step 8: Set Permissions (VERY IMPORTANT)

```bash
chmod 700 /home/sanket/.ssh
chmod 600 /home/sanket/.ssh/authorized_keys
chown -R sanket:sanket /home/sanket
```

---

## Step 9: Connect Using SSH Key

```bash
ssh -i localkey sanket@your-public-ip
```

---

## ✅ Output

- Successfully logged in without password
- SSH authentication done using key pair
