# ansible-devops-playbooks


# Description
This is a repository for storing DevOps Ansible Playbooks that can be used to configure provisioned instances.

# Playbooks
Playbook | Description
--- | ---
devops_toolset | A minimal install which allows docker to be used thereafter for containerized development

# Usage
The following docker image can be used to run the ansible code -

grababyte/ubuntu-devops-toolset:latest

# Requirements
All playbooks call roles which are sourced from Ansible Galaxy

`ansible-galaxy install --force -r requirement.yml -p roles`

## Run Ansible
To run ansible code residing in your local path -

```
docker run -d \
  -v ${PWD}:/var/workspace \
  -w /var/workspace \
  grababyte/ubuntu-devops-toolset:latest \
  ansible-playbook <relative_path_to_playbook> \
    -i <relative_path_to_inventory> \
    -e key="${value}" \
    -e key="${value}" \
    -e key="${value}"
```

Alternatively, install ansible with either yum (RedHat), apk (Alpine} or apt (Debian) and run locally -

```
ansible-playbook <relative_path_to_playbook> \
  -i <relative_path_to_inventory \
  -e key="${value}" \
  -e key="${value}" \
  -e key="${value}"
```

## Author
This repository has been maintained by GrabAByte since 2023.
