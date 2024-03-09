# Chatwoot Installation Guide

This guide provides step-by-step instructions for installing Chatwoot on your server. Chatwoot is an open-source customer engagement suite, perfect for managing your customer conversations across various channels.

## Prerequisites

- A server running a Linux distribution (Ubuntu recommended).
- `wget` installed on your server.
- Root access or a user with sudo privileges.

## Installation Steps

1. **Download the Installation Script**

   First, download the Chatwoot installation script using `wget`.

   ```bash
   wget https://get.chatwoot.app/linux/install.sh
   ```

2. **Make the Script Executable**

   Change the script's permissions to make it executable.

   ```bash
   chmod +x install.sh
   ```

3. **Run the Installation Script**

   Start the installation process by executing the script.

   ```bash
   ./install.sh --install
   ```

   During the installation process, you'll be prompted to make several choices. Select **"yes"** for all prompts to continue with the default options.

4. **Set Up Your Domain**

   When asked, enter your desired subdomain (e.g., `chat.domain.com`). This will be used to access your Chatwoot installation.

## Post-Installation Configuration

After the installation, a few additional steps are required to finalize the setup.

1. **Verify Domain Configuration**

   Check if your domain is correctly specified in the `.env` configuration file.

2. **Change the Chatwoot User Password**

   For security reasons, it's recommended to change the default password for the `chatwoot` user.

   ```bash
   passwd chatwoot
   ```

   Enter and confirm your chosen password when prompted.

3. **Log In as the Chatwoot User**

   Switch to the `chatwoot` user and navigate to the Chatwoot directory.

   ```bash
   sudo -i -u chatwoot
   cd chatwoot
   ```

4. **Edit the `.env` File**

   You may need to make additional configurations or verify settings in the `.env` file.

   ```bash
   nano .env
   ```

   Make any necessary changes and save the file.

5. **Restart Chatwoot**

   Apply the changes by restarting the Chatwoot services.

   ```bash
   sudo systemctl restart chatwoot.target
   ```

## Conclusion

Your Chatwoot installation should now be up and running. Access it via your configured subdomain and begin setting up your customer engagement suite. For further customization and usage details, refer to the [official Chatwoot documentation](https://www.chatwoot.com/docs/self-hosted/deployment/linux-vm?utm_source=cwctl).
