# Chrony Time Synchronization Role
=========

This Ansible role installs and configures Chrony for time synchronization, sets the system timezone, and ensures the service is properly running on the target system.

Requirements
------------

This role requires a Linux distribution that supports Chrony, such as Ubuntu, Debian, or CentOS. No additional dependencies or prerequisites are needed beyond Ansible itself.

## Tasks Overview

- **Install Chrony Package**: Installs the `chrony` package, which is used for time synchronization on Linux systems.
- **Configure Timezone**: Sets the system timezone to `America/Sao_Paulo` using the `timedatectl` command, ensuring the correct regional time settings.
- **Enable and Start Chrony Service**: Ensures that the `chrony` service is enabled to start at boot and is currently running.
- **Verify Time Synchronization**: Checks if `chrony` is properly synchronizing the system time. It registers the output of the `chronyc tracking` command and fails the play if time synchronization is not normal.
- **Display Current Date and Time**: Captures and displays the current system date and time to provide a clear output of the current settings.
- **Show Chrony Status**: Outputs the current date and time using the `debug` module, allowing you to confirm that the time configuration is correct.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - {role: chrony, tags: Chrony}


License
-------
MIT License

Author Information
------------------

This role was created in 2024 by [Francisco Wesley](https://github.com/FWesleycosta).

