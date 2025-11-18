# Dev-stack-and-pack-stack-

✅ 1. What is DevStack?

DevStack is a collection of scripts used to install and run OpenStack for development and testing.
It is mainly used by developers to understand and test OpenStack services.

Features

Lightweight

For development/testing (NOT production)

Easy to install using a single script



---

🖥️ DevStack Installation Steps (Quick)

Prerequisites

Ubuntu Server 20.04/22.04

Minimum 8 GB RAM

sudo user



---

Commands

1. Update system

sudo apt update && sudo apt upgrade -y

2. Install required packages

sudo apt install git -y

3. Clone DevStack

git clone https://opendev.org/openstack/devstack
cd devstack

4. Create local.conf

sudo nano local.conf

Paste:

[[local|localrc]]
ADMIN_PASSWORD=admin
DATABASE_PASSWORD=admin
RABBIT_PASSWORD=admin
SERVICE_PASSWORD=admin

Save & exit.

5. Start installation

./stack.sh

💡 Takes ~20–40 minutes.


---


---

📦 2. What is Packstack?

Packstack is a tool used to install OpenStack using Puppet modules.
It is used for Proof-of-Concept (POC) or small deployments.

Features

For CentOS/RHEL based systems

Semi-production environment

Uses bash + Puppet automation



---

🖥️ Packstack Installation Steps (Quick)

Prerequisites

CentOS Stream 8 / RHEL 8

Minimum 8 GB RAM

Root access



---

Commands

1. Update system

sudo dnf update -y

2. Enable OpenStack repository

sudo dnf install -y centos-release-openstack-yoga
sudo dnf update -y

3. Install Packstack

sudo dnf install -y openstack-packstack

4. Install OpenStack using Packstack

packstack --allinone

💡 Takes ~30–45 minutes.


---


---

🔐 3. PuTTY SSH Connection (Quick Note)

What is PuTTY?

PuTTY is a free SSH client used to remotely connect to servers.


---

How to Use PuTTY for SSH

1. Open PuTTY

2. Enter your server IP

Example:

192.168.1.100

3. Set Port

22

4. Select Connection Type

SSH

5. Click 'Open'

6. Login in terminal

username: your_username
password: your_password


---

🔑 If using private key (.ppk):

Go to:

Connection → SSH → Auth → Credentials → Browse → Select Key

Then Open → Login.


---

🎯 Short Difference (DevStack vs Packstack)

Feature	DevStack	Packstack

Purpose	Development/testing	POC/small deployment
OS	Ubuntu	CentOS/RHEL
Complexity	Easy	Medium
Stability	Not stable	More stable
