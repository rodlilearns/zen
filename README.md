# zen
This is an Ansible project to demonstrate how organisations can automate certain configurations in their Linux systems.
The example configurations include patching, selinux, services, firewall.

## How to use (patch localhost):
1. In the `patch.yml` playbook, ensure you have set the correct hosts to target (localhost).
2. In the `patch.yml` playbook, ensure you have the required packages to update/install.
3. In the command line, change your directory to the Ansible project i.e. ~/zen
4. In the command line, type `ansible-playbook patch.yml -K` The `-K` option prompts you for your root password. This is needed for patching.
5. In the command line, when prompted, type your root password.
6. The automation will now run.

## How to use (patch multiple servers):
1. In the `patch.yml` playbook, ensure you have set the correct hosts to target (e.g. `servers_that_need_patching`).
2. In the `inventory` file, ensure you have set the correct hosts under `servers_that_need_patching`.
3. In the `ansible.cfg` file, ensure you have set the correct inventory file path (e.g. `./inventory`). This action will tell Ansible to look for hosts within this particular inventory file.
4. In the `patch.yml` playbook, ensure you have the required packages to update/install.
5. In the command line, change your directory to the Ansible project i.e. ~/zen
6. In the command line, type `ansible-playbook patch.yml -K` The `-K` option prompts you for your root password. This is needed for patching.
7. In the command line, when prompted, type your root password.
8. The automation will now run.

## How to use roles
When playbooks become long and complicated, roles are used to simplify them. Further, roles are more easily transportable across different playbooks.
1. Create a role using the `ansible-galaxy init` command. (e.g. `ansible-galaxy init ./roles/patch`). This command will create a directory for patch under `./roles/` called `patch`, and populate it with more directories which may be useful for the role.
2. Add tasks to `./roles/patch/tasks/main.yml`.
3. Add the role to a playbook (e.g. `./system.yml`)
4. In the command line, change your directory to the Ansible project i.e. ~/zen
5. In the command line, type `ansible-playbook system.yml -K` The `-K` option prompts you for your root password. This is needed for patching.
6. In the command line, when prompted, type your root password.
7. The automation will now run.

