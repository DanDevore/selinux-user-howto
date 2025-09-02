# selinux-user-howto

# 🔐 SELinux User Mapping Tutorial + Script

This repository provides a **step-by-step guide** and a **simple automation script** for creating a new Linux user and mapping it to an SELinux user.  

Whether you want to learn the manual process or quickly set it up with the included script, this repo will walk you through both approaches.

## Prerequisites
- SELinux enabled (`getenforce` shows *Enforcing* or *Permissive*)
- `semanage` installed  
  - RHEL/Fedora: `sudo dnf install policycoreutils-python-utils -y`  
  - Debian/Ubuntu: `sudo apt-get install policycoreutils selinux-basics selinux-policy-default -y`
