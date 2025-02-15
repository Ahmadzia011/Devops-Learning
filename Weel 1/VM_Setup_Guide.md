🖥️ Virtual Machine Setup Guide
Introduction


In this guide, I will walk through two methods for setting up a Virtual Machine (VM) for DevOps practice:

1️⃣ Manual Setup (Using VirtualBox)
2️⃣ Automatic Setup (Using Vagrant)


# Manual VM Setup (Windows & Ubuntu)

## Step 1: Install VirtualBox
- **Windows & Ubuntu**: Download and install [VirtualBox](https://www.virtualbox.org/)

## Step 2: Download a Linux ISO
- Download the `.iso` file for the Linux distribution of your choice.
- I downloaded **CentOS 9** and **Ubuntu**.

## Step 3: Create a New VM in VirtualBox

1. **Open VirtualBox** → Click **New**.
2. **Name the VM** (e.g., `Ubuntu-DevOps`).
3. Keep default settings unless you want to adjust **hard disk** and **memory allocation**.
4. Click **Finish** to create the VM.

### 🛠 Install OS on the VM
1. Open **Settings** → Go to **Storage**.
2. Under **Controller: IDE**, add the `.iso` file.
3. Go to **Network** → **Adapter 2** → Enable **Network Adapter** → Set to **Bridged Adapter**.
4. Go to **System** → **Motherboard** tab → Set **Pointing Device** to **USB Tablet**.
5. Click **OK**, then **Start the VM**.

---

# Automatic VM Setup (Using Vagrant & VirtualBox)

## Step 1: Install Vagrant & VirtualBox
- **Windows & Ubuntu**: Download and install both from:  
  - [VirtualBox](https://www.virtualbox.org/)  
  - [Vagrant](https://developer.hashicorp.com/vagrant/downloads)  

## Step 2: Set Up the VM with Vagrant

1. **Initialize Vagrant with a Base Box**  
   Run the following command to initialize a Vagrant environment with your preferred OS image (from [Vagrant Cloud](https://app.vagrantup.com/)):  
   ```sh

   vagrant init <box-name>

2. **Start the VM**
   Navigate to the folder where your Vagrantfile is located and run:
      ```sh
      vagrant up

3. **Access the VM via SSH**
   Once the VM is running, log in using:
   ```sh
    vagrant ssh


📌 Conclusion
Both methods allow you to set up a Virtual Machine, but:
✅ Manual Method gives full control over the setup
✅ Automatic Method (Vagrant) makes setup faster & reproducible
