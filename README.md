
## DevStack Install on Ubuntu18.4

Step-1: Update your os and reboot
~~~
apt-get update && reboot
~~~

Step-2: Create a sudo user and Enable sudo privileges for this user without need for a password.
~~~
sudo useradd -s /bin/bash -d /opt/stack -m stack
echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack
~~~
Step-3: Login with stack user
~~~
su - stack
sudo apt install git -y
git clone https://git.openstack.org/openstack-dev/devstack
cd devstack
~~~
Step-4: Create local.conf file and paste below configuration
~~~
vim local.conf
[[local|localrc]]

# Password for KeyStone, Database, RabbitMQ and Service
ADMIN_PASSWORD=StrongAdminSecret
DATABASE_PASSWORD=$ADMIN_PASSWORD
RABBIT_PASSWORD=$ADMIN_PASSWORD
SERVICE_PASSWORD=$ADMIN_PASSWORD
~~~
Step-5: Start Devstack Installation
~~~
./stack.sh
~~~


After Successfully Installed. visit https://server-ip/dashboard
### The following features will be installed:
~~~
Horizon – OpenStack Dashboard
Nova – Compute Service
Glance – Image Service
Neutron – Network Service
Keystone – Identity Service
Cinder – Block Storage Service
Placement – Placement API
~~~
DevStack Remove Command
~~~~
./clean.sh
./unstack.sh
~~~~





