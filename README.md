# Automated OS Deployment Lab (MDT + WDS + PXE Boot)

This project showcases a complete network-based operating system deployment environment using **Microsoft Deployment Toolkit (MDT)** and **Windows Deployment Services (WDS)**.

I built this lab to automate the imaging process for Windows 11 (24H2) systems — enabling PXE boot, driver management, and application deployment — all through an unattended setup.

---

## 🖥️ Overview

Instead of manually installing Windows on each machine, I configured a **PXE boot** workflow that allows any client device on the network to boot directly into the deployment share and install a fully configured Windows image.

### Key Components

- **MDT Deployment Share** (hosted on Windows Server)
- **Windows Deployment Services (WDS)** for PXE network boot
- **Windows 11 24H2 ISO** imported into MDT
- **Out-of-Box Drivers** for ZBook, Dell, EliteBook, and other systems
- **Task Sequences** to automate installation, drivers, and post-setup apps

---

## 🧩 What I Did

1. Accessed the Windows Server remotely via **RDP**
2. Mapped a drive to import the **Windows 11 24H2 ISO**
3. Created a new **MDT Deployment Share**
4. Imported multiple **Windows 11 editions** into MDT (Education, Pro, N, etc.)
5. Added **drivers** and **applications** (Google Chrome, Workspace Sync, NinjaOne)
6. Configured **Task Sequences** to automate installation and post-deployment
7. Integrated with **WDS** to enable PXE boot from the network

---

## 📸 Screenshots

| Deployment Workbench | Operating Systems |
|-----------------------|-------------------|
| ![Deployment Workbench](images/deployment_workbench.png) | ![Operating Systems](images/operating_systems.png) |

*(My screenshots are added in `/images` folder and named them accordingly.)*

---

## 🧠 What I Learned

- Understanding how MDT and WDS integrate for scalable OS deployment
- Automating application installs, drivers, and updates through task sequences
- Managing and customizing Windows images
- Streamlining system provisioning for faster rollout and recovery

---

## 🛠️ Next Step: Terraform + Infrastructure as Code (IaC)

The next phase of this project is to use **Terraform** to **automate provisioning** of the deployment infrastructure.

Planned enhancements:
- Define the **MDT/WDS Server** as code (Azure VM or local Hyper-V VM)
- Automate **network, storage, and security group configuration**
- Deploy the PXE boot lab with a single command:

```bash
terraform apply
