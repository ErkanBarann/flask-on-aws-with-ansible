
# Ansible AWS Flask Deployment

This project provides a fully integrated deployment setup using **Ansible** on **AWS EC2**, consisting of a **Python Flask application**, a **MySQL database**, and an **NGINX reverse proxy** — all running in Docker containers.

## 🛠️ Project Overview

- The Flask application is deployed inside a Docker container.
- The MySQL database runs in a separate container on another EC2 instance.
- NGINX acts as a reverse proxy, directing traffic to the Flask app.
- All components are automatically set up and managed via Ansible playbooks.

## 📦 Technologies Used

- **Ansible** (Configuration Management)
- **AWS EC2** (Cloud Infrastructure)
- **Docker** (Containerization)
- **Python Flask** (Web Application)
- **MySQL** (Database)
- **NGINX** (Reverse Proxy)

## 📂 Project Structure

```bash
ansible-project/
├── ansible.cfg
├── inventory/
│   └── dynamic_inventory.yml
├── playbook.yml
├── roles/
│   ├── app/
│   │   └── tasks/main.yml
│   ├── db/
│   │   └── tasks/main.yml
│   ├── nginx/
│   │   └── tasks/main.yml
```

## 🚀 What Was Done with Ansible?

✅ Created essential Ansible roles:
- `app` role: Installs Docker, builds Flask image, runs the container.
- `db` role: Installs Docker, runs the MySQL container.
- `nginx` role: Installs Docker, runs the NGINX container.

✅ EC2 instances were manually launched via the AWS Console and accessed via Ansible.

✅ A Route53 DNS record was configured manually to route traffic to the NGINX instance.

✅ All services were automated using the following command:

```bash
ansible-playbook -i inventory/dynamic_inventory.yml playbook.yml
```

## ⚙️ Requirements

- Python 3.x
- Ansible 2.10+
- AWS EC2 Access with SSH key configured
- AWS Security Groups allowing:
  - Port 22 (SSH)
  - Port 8000 (Flask)
  - Port 3306 (MySQL)
  - Port 80 (NGINX)

## 📌 Notes

- EC2 instance type used: `t2.micro`
- Flask application listens on `PORT 8000`
- All services are structured for a production-ready environment

---

## 👨‍💻 Contributor

- **Erkan [Ingolstadt, DE]** – Project Developer & DevOps Student

---


