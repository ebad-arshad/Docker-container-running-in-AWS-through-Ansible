# Docker Orchestration on AWS via Ansible

This repository demonstrates the automated deployment and management of Docker containers on AWS EC2 instances using **Ansible**. It moves beyond simple shell scripting by utilizing the official `community.docker` collection to achieve a declarative, idempotent infrastructure state.



## 🎯 Project Objectives

* **Automated Provisioning:** Bridging the gap between a raw Ubuntu 24.04 LTS instance and a production-ready Docker host.
* **Idempotent Deployment:** Ensuring that re-running the playbook maintains the desired state without creating conflicts or duplicate containers.
* **Advanced Connection Management:** Utilizing mid-playbook connection resets to apply Linux group permission changes without manual intervention.

---

## 🛠 Tech Stack

- **Automation Engine:** Ansible (using `community.docker` collection)
- **Host Provider:** AWS (EC2)
- **Containerization:** Docker
- **Python Integration:** Docker SDK for Python (`python3-docker`)

---

## 📂 Key Components

* **`inventory.ini`**: Defines the target AWS host and SSH connection details.
* **`main.yml`**: The master playbook containing tasks for system updates, Docker engine installation, and container deployment.

---

## 🚀 Execution Guide

1. **Prerequisites:**
   * An AWS EC2 instance running Ubuntu.
   * Local machine with Ansible installed.
   * Official Docker collection installed:
     ```bash
     ansible-galaxy collection install community.docker
     ```

2. **Run the Playbook:**
   ```bash
   ansible-playbook -i inventory.ini main.yml
