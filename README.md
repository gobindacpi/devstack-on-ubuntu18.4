# devstack-on-ubuntu18.4

DevStack Install on Ubuntu18.4
---
---
Step-1: Update your os and reboot
---
---
apt-get update && reboot
---
Step-2: Create a sudo user and Enable sudo privileges for this user without need for a password.
---
sudo useradd -s /bin/bash -d /opt/stack -m stack
echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack
---


