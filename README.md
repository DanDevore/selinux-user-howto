# selinux-user-howto

# 🔐 SELinux User Mapping Tutorial + Script

This repository provides a **step-by-step guide** and a **simple automation script** for creating a new Linux user and mapping it to an SELinux user.  

Whether you want to learn the manual process or quickly set it up with the included script, this repo will walk you through both approaches.

## Prerequisites
- SELinux enabled (`getenforce` shows *Enforcing* or *Permissive*)
- `semanage` installed  
  - RHEL/Fedora: `sudo dnf install policycoreutils-python-utils -y`  
  - Debian/Ubuntu: `sudo apt-get install policycoreutils selinux-basics selinux-policy-default -y`
 
## 📖 Manual Steps

### 1. Create the Linux user and map it to the "staff_u" SElinux user
```bash
sudo useradd -Z staff_u dan
sudo passwd dan
```

### 2. Verify the mapping
```bash
sudo semanage login -l | grep dan
```

### 3. Relabel the new user's directory
```bash
sudo restorecon -RF -v /home/dan
```

### 4. Logout and log back in as the new user dan and verify the mapping
```bash
id -Z
```


