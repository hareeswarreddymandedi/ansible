# Ansible Fundamentals

Numbered playbooks covering host connectivity, Nginx installation, and variable sources.

## Repository guide

- [inventory.ini](inventory.ini): sample host groups and inventory variables.
- [01-playbook.yaml](01-playbook.yaml): connectivity check against the frontend group.
- [03-nginx.yaml](03-nginx.yaml): install Nginx and enable its service.
- `04-vars.yaml` through `08-vars.yaml`: variable exercises.
- [course.yaml](course.yaml): supporting variable data.

## Getting started

Use an Ansible control node with SSH access to your own Linux lab hosts. Replace the sample inventory addresses and configure your SSH user and key before running a playbook.

```bash
ansible-inventory -i inventory.ini --graph
ansible-playbook -i inventory.ini 01-playbook.yaml --syntax-check
ansible-playbook -i inventory.ini 01-playbook.yaml
ansible-playbook -i inventory.ini 03-nginx.yaml --check
```

The Nginx playbook requires privilege escalation. Review check-mode results before an actual run; check mode is not a guarantee that every task will succeed.

## Status

Learning examples, with environment-specific inventory. Validate each playbook independently before use.
