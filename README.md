# Automated Multi-Environment Infrastructure Management with Ansible

Automated configuration and deployment across a multi-tier AWS EC2 architecture using Ansible from a centralized Ubuntu control node.

---

## Architecture Overview

The infrastructure consists of 7 AWS EC2 instances running Ubuntu:
* **Control Node (1):** Central management node executing Ansible playbooks and tracking version control.
* **Target Nodes (6):**
  * `dev` (2 instances): Development environment.
  * `testing` (2 instances): QA/Test environment.
  * `prod` (2 instances): Production environment.

---

## Project Structure

```text
ansible-infra-project/
├── ansible.cfg          # Ansible configuration (inventory path, SSH settings, auto python interpreter)
├── inventory.ini        # Environment-based host groupings ([dev], [testing], [prod])
├── install_python.yml   # Targeted configuration playbook
├── .gitignore           # Ignores sensitive keys (*.pem, id_rsa) and local caches
└── README.md            # Project documentation
