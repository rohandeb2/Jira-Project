# 🚀 Terraform One-Shot Setup

<div align="center">
  
![Terraform](https://img.shields.io/badge/terraform-%235835CC.svg?style=for-the-badge&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

</div>

## 📋 Table of Contents
- [Overview](#overview)
- [Setup on AWS EC2](#setup-on-aws-ec2)
- [Setup on Local Machine](#setup-on-local-machine)
- [Terraform Installation](#terraform-installation)
- [Verification](#verification)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## 🔍 Overview

This guide provides step-by-step instructions for setting up Terraform on both AWS EC2 instances and local machines. Terraform is an infrastructure as code (IaC) tool that allows you to build, change, and version infrastructure safely and efficiently.

## ⚙️ Setup on AWS EC2

### Creating an EC2 Instance

1. You can create an EC2 instance as we learned earlier
2. [Click here to see EC2 instance creation guide](#) <!-- Add your EC2 creation link here -->

### Connecting to Your EC2 Instance

```bash
ssh -i "your-key.pem" ec2-user@your-instance-public-dns
```

## 💻 Setup on Local Machine

Skip to the [Terraform Installation](#terraform-installation) section if you're setting up on your local machine.

## 🔧 Terraform Installation

Navigate to the [official Terraform documentation](https://developer.hashicorp.com/terraform/downloads) for platform-specific installation instructions. Below are the steps for Linux:

### For Linux (Ubuntu/Debian)

#### 1. Ensure your system is updated

```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```

#### 2. Install the HashiCorp GPG key

```bash
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
```

#### 3. Verify the key's fingerprint

```bash
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
```

The GPG command will report the key fingerprint:

```
/usr/share/keyrings/hashicorp-archive-keyring.gpg
-------------------------------------------------
pub   rsa4096 XXXX-XX-XX [SC]
      AAAA AAAA AAAA AAAA
uid   [ unknown] HashiCorp Security (HashiCorp Package Signing) <security+packaging@hashicorp.com>
sub   rsa4096 XXXX-XX-XX [E]
```

#### 4. Add the official HashiCorp repository

```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```

#### 5. Download package information from HashiCorp

```bash
sudo apt update
```

#### 6. Install Terraform

```bash
sudo apt-get install terraform
```

### For macOS

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```

### For Windows

1. Download the appropriate package from the [Terraform website](https://www.terraform.io/downloads.html)
2. Extract the package to a folder included in your system's PATH

## ✅ Verification

After installation, verify that Terraform is installed correctly:

```bash
terraform --version
```

You should see output similar to:
```
Terraform v1.5.0
on linux_amd64
```

## ❓ Troubleshooting

If you encounter any issues during installation:

1. Ensure your system meets the [requirements](https://learn.hashicorp.com/tutorials/terraform/install-cli)
2. Check for any error messages during the installation process
3. Verify your network connection if downloading packages fails
4. For permission-related issues, ensure you're using `sudo` when needed

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

<div align="center">
  <p>Made with ❤️ for infrastructure automation</p>
</div>
