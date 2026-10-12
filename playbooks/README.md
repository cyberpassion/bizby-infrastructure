# Bizby Ansible Playbooks

These playbooks are starter examples for your existing `bizby-infrastructure` repository.
They are designed to be copied into the repository's `playbooks/` directory.

## Included playbooks

- `server-audit.yml` — read-only operating-system, memory, disk, and service checks.
- `install-packages.yml` — installs a small, explicit package list. **Do not run until reviewed.**
- `configure-nginx.yml` — validates Nginx configuration and reports service status; it does not overwrite site configuration.
- `configure-php.yml` — reports PHP-FPM status and installed PHP version; it does not modify PHP settings.
- `configure-redis.yml` — reports Redis status; it does not modify Redis configuration.
- `setup-firewall.yml` — example UFW status inspection only; it does not change firewall rules.
- `deploy-laravel.yml` — placeholder safety guard, intentionally fails until you define and review a deployment process.
- `restart-services.yml` — placeholder safety guard, intentionally fails until you explicitly define allowed services.

## Before running

1. Review each playbook.
2. Start with the read-only audit:
   ```bash
   ~/.venvs/ansible/bin/ansible-playbook playbooks/server-audit.yml
   ```
3. These playbooks use `hosts: staging` to match the current inventory.
4. Privilege escalation (`become: true`) is enabled only where package installation requires it.
5. Never commit private SSH keys, passwords, or secrets to Git.

The package installer currently names Nginx, PHP 8.3 FPM, and Redis. This is only an example package list, not a recommendation to change your existing server. Review it first; it does not configure Laravel, PHP extensions, Nginx virtual hosts, database access, TLS, or firewall rules.
