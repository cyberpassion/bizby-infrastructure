# Bizby Infrastructure

Infrastructure automation for Bizby using Ansible.

## Environments

- Staging
- Production

## Safety

- Never commit secrets, private keys, or environment files.
- Test playbooks against staging before production.
- Use Ansible Vault for encrypted secrets.
- Review changes before running production playbooks.
