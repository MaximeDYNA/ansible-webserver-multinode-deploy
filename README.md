
# ansible-webserver-multinode-deploy

## 📋 Project Description

This project uses **Vagrant** and **Ansible** to automate the setup of a simple multi-node web infrastructure composed of three servers:
- **Ansible Controller**: Manages the deployment process.
- **Web Server Host**: Runs an **Apache HTTP Server**.
- **Database Server Host**: Runs a **PostgreSQL** database.

The goal is to demonstrate the provisioning and configuration of a basic web application stack (Web + Database) using Infrastructure as Code (IaC) principles.

## 🚀 Project Workflow

1. **Provisioning**:
   - Vagrant provisions three virtual machines using **VMware** as the hypervisor.

2. **Configuration**:
   - Ansible is installed on the controller server.
   - A single Ansible playbook (`playbook.yml`) is used to:
     - Deploy and configure **Apache** on the web server host.
     - Deploy and configure **PostgreSQL** on the database server host.

3. **Validation**:
   - Ensure both Apache and PostgreSQL services are up and running after deployment.

## 🛠️ Technologies Used

- **Vagrant**: Virtual machine provisioning and management.
- **VMware**: Virtualization hypervisor.
- **Ansible**: Configuration management and orchestration tool.
- **Apache HTTP Server**: Web server installed on the web host.
- **PostgreSQL**: Database server installed on the database host.

## 📦 Project Structure

```
├── Vagrantfile          # Defines the Vagrant VM setup
├── ansible/
│   ├── hosts           # Inventory file with hosts definitions
│   ├── playbook.yml     # Playbook for installing and configuring Apache and PostgreSQL
│   └── roles/           # Optional roles structure
├── README.md            # Project documentation
```

## ⚙️ Prerequisites

- Vagrant installed
- VMware Workstation or VMware Fusion
- Vagrant VMware provider plugin
- Ansible installed on your local machine (optional for testing)

## 🚀 Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/MaximeDYNA/ansible-webserver-multinode-deploy.git
   cd ansible-webserver-multinode-deploy
   ```

2. Start the VMs using Vagrant:
   ```bash
   vagrant up
   ```

3. SSH into the Ansible Controller:
   ```bash
   vagrant ssh controller
   ```

4. Run the Ansible playbook from the controller:
   ```bash
   ansible-playbook -i ansible/hosts ansible/playbook.yml
   ```

## 👨‍💻 Author

- [Maxime DYNA](https://github.com/MaximeDYNA)

## 📄 License

This project is licensed under the MIT License.
