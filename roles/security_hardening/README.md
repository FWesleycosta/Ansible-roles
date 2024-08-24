# Linux System Hardening Role

This Ansible role performs comprehensive system hardening for a Linux server. It includes tasks to secure SSH configuration, manage user privileges, enforce password policies, set file and directory permissions, configure auditd rules, and more. The role is designed to enhance the overall security posture of the system.

## Requirements

This role is compatible with Debian/Ubuntu-based systems. Ensure that Ansible is installed and configured properly, and that target hosts are accessible via SSH.

## Tasks Overview

- **Find and Manage Log Files**: Locates all files in the `/var/log` directory and sets appropriate permissions based on whether they are files or directories.
- **Configure Sudoers**: Ensures the sudoers file contains the correct configurations, including adding the `%wheel` group.
- **Secure SSH Configuration**: Disables root login, enforces password authentication, and configures multiple SSH options to strengthen security.
- **Password Policy Enforcement**: Configures PAM to enforce password complexity, lockout settings, and other account security measures.
- **Auditd Configuration**: Sets up auditd rules to monitor sensitive files and system changes, ensuring compliance and auditing.
- **File and Directory Permissions**: Sets strict permissions on sensitive files such as `/etc/shadow`, `/etc/sudoers`, and others.
- **Sysctl Configuration**: Hardens network and kernel settings via sysctl parameters to prevent common attacks.
- **USB Storage Restriction**: Disables USB storage devices by blacklisting the `usb-storage` module.
- **Automatic Security Updates**: Installs and configures `unattended-upgrades` to automatically apply security updates.
- **Fail2ban Setup**: Installs and configures Fail2ban to prevent brute-force attacks on SSH.
- **Session Timeout**: Sets a terminal session timeout to automatically log out inactive users.
- **Rsyslog Configuration**: Ensures logs are forwarded to a remote server for centralized monitoring.
- **PAM Login Lockout**: Configures PAM to lock user accounts after multiple failed login attempts.

## Dependencies

This role has no external dependencies.

## Example Playbook

Here is an example of how to use this role:

```yaml
- hosts: servers
  roles:
    - { role: hardening, tags: security_hardening }
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author Information
 
This role was created in 2024 by [Francisco Wesley](https://github.com/FWesleycosta).