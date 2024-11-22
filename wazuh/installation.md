# Wazuh Download and Installation Guide

This guide provides instructions for downloading and setting up Wazuh components, including the Wazuh Manager, Wazuh Agent, and Wazuh Dashboard.

---

## Step 1: Download Wazuh Components

### 1. Wazuh Manager

**For Debian/Ubuntu**:
1. Add the Wazuh repository:
   ```bash
   curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -
   echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
   ```
2. Update and install:
   ```bash
   sudo apt update
   sudo apt install wazuh-manager -y
   ```

**For CentOS/RHEL**:
1. Add the Wazuh repository:
   ```bash
   sudo rpm --import https://packages.wazuh.com/key/GPG-KEY-WAZUH
   cat << EOF | sudo tee /etc/yum.repos.d/wazuh.repo
   [wazuh]
   gpgcheck=1
   gpgkey=https://packages.wazuh.com/key/GPG-KEY-WAZUH
   enabled=1
   name=Wazuh repository
   baseurl=https://packages.wazuh.com/4.x/yum/
   EOF
   ```
2. Update and install:
   ```bash
   sudo yum install wazuh-manager -y
   ```

---

### 2. Wazuh Agent

**For Debian/Ubuntu**:
1. Add the Wazuh repository:
   ```bash
   curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -
   echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
   ```
2. Update and install:
   ```bash
   sudo apt update
   sudo apt install wazuh-agent -y
   ```

**For CentOS/RHEL**:
1. Add the Wazuh repository:
   ```bash
   sudo rpm --import https://packages.wazuh.com/key/GPG-KEY-WAZUH
   cat << EOF | sudo tee /etc/yum.repos.d/wazuh.repo
   [wazuh]
   gpgcheck=1
   gpgkey=https://packages.wazuh.com/key/GPG-KEY-WAZUH
   enabled=1
   name=Wazuh repository
   baseurl=https://packages.wazuh.com/4.x/yum/
   EOF
   ```
2. Update and install:
   ```bash
   sudo yum install wazuh-agent -y
   ```

**For Windows**:
1. Visit the [Wazuh Downloads Page](https://wazuh.com/downloads/) to download the Windows Agent installer.
2. Run the installer and follow the setup instructions.

---

### 3. Wazuh Dashboard

**For Debian/Ubuntu**:
1. Install Node.js and the Wazuh Dashboard package:
   ```bash
   curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
   sudo apt install nodejs wazuh-dashboard -y
   ```

2. Start and enable the Wazuh Dashboard:
   ```bash
   sudo systemctl start wazuh-dashboard
   sudo systemctl enable wazuh-dashboard
   ```

**For CentOS/RHEL**:
1. Install Node.js and the Wazuh Dashboard package:
   ```bash
   curl -sL https://rpm.nodesource.com/setup_16.x | sudo bash -
   sudo yum install nodejs wazuh-dashboard -y
   ```

2. Start and enable the Wazuh Dashboard:
   ```bash
   sudo systemctl start wazuh-dashboard
   sudo systemctl enable wazuh-dashboard
   ```

---

## Step 2: Configure Components

1. **Configure the Manager**:
   - Edit the `ossec.conf` file located in `/var/ossec/etc/` to customize manager settings.

2. **Configure the Agent**:
   - Set the manager’s IP address in the agent configuration file (`/var/ossec/etc/ossec.conf`).

3. **Access the Dashboard**:
   - Open a browser and navigate to `http://<YOUR_SERVER_IP>:5601`.
   - Log in using the default credentials:
     - Username: `admin`
     - Password: `admin`

---

## Additional Resources

- [Wazuh Documentation](https://documentation.wazuh.com/)  
- [Wazuh GitHub Repository](https://github.com/wazuh/wazuh)  
- [Community Support Forum](https://wazuh.com/community/)

By following these steps, you can successfully download and install Wazuh components for your network security setup.
