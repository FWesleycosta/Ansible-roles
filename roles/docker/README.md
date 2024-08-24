Docker Role
=========

This role installs Docker on a host machine. It is based on the official Docker installation guide for Ubuntu.

Requirements
------------

This role is compatible with Debian/Ubuntu-based systems. Ensure that Ansible is configured and the target hosts are accessible.

Tasks Overview
--------------

This playbook performs the following steps to configure and install Docker, Docker Compose, and related settings on the system:

- **Update and Upgrade Packages**: Updates the system packages and performs an upgrade to the latest versions.
- **Install Required Packages**: Installs essential packages like `curl`, `gnupg`, and `lsb-release` needed for the environment.
- **Check if Docker is Installed**: Checks if Docker is already installed on the system.
- **Download Docker Installation Script**: Downloads the Docker installation script if it is not present.
- **Execute Docker Installation Script**: Runs the script to install Docker.
- **Add Docker Group**: Adds the `docker` group to the system.
- **Add User to Docker Group**: Adds the current user to the `docker` group to allow Docker commands without `sudo`.
- **Create Directories for Docker Configurations**: Creates the necessary directories for Docker configurations.
- **Add Configuration for Docker Daemon**: Adds specific configurations for the Docker daemon.
- **Add Log Rotation Configuration for Docker Containers**: Sets up log rotation configurations for Docker containers.
- **Install Docker Compose**: Installs Docker Compose for managing multi-service containers.
- **Enable and Start Docker Services**: Enables and starts the Docker and containerd services.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: docker, tags: docker }

License
-------
MIT License

Author Information
------------------
This role was created in 2024 by [Francisco Wesley](https://github.com/FWesleycosta).