# Expense Ansible Project

This project contains Ansible playbooks to deploy a three-tier expense tracking application. The application consists of a frontend, a backend, and a MySQL database.

## Project Structure

- `ansible.cfg`: Ansible configuration file. It sets the default inventory file.
- `backend.service`: Systemd service file for the backend application.
- `backend.yaml`: Ansible playbook to configure the backend server.
- `expense.conf`: Nginx configuration file for the frontend.
- `frontend.yaml`: Ansible playbook to configure the frontend server.
- `inventory.ini`: Ansible inventory file. It defines the hosts for each tier of the application.
- `mysql.yaml`: Ansible playbook to configure the MySQL database server.

## Application Tiers

The application is divided into three tiers:

- **Frontend:** A web interface for users to interact with the application. It is served by Nginx.
- **Backend:** A Node.js application that provides the API for the frontend.
- **Database:** A MySQL database to store the application data.

## How to Use

1. **Install Ansible:** Make sure you have Ansible installed on your machine.
2. **Update Inventory:** Edit the `inventory.ini` file to match your server hostnames or IP addresses.
3. **Run Playbooks:** Run the playbooks in the following order:
    ```bash
    ansible-playbook mysql.yaml
    ansible-playbook backend.yaml
    ansible-playbook frontend.yaml
    ```

## Playbook Details

### `mysql.yaml`

This playbook configures the MySQL server. It installs the necessary packages, starts the MySQL service, and sets the root password.

### `backend.yaml`

This playbook configures the backend server. It installs Node.js, downloads the backend application code, installs the dependencies, and sets up a systemd service to run the application.

### `frontend.yaml`

This playbook configures the frontend server. It installs Nginx, downloads the frontend application code, and configures Nginx to serve the frontend and proxy API requests to the backend.
