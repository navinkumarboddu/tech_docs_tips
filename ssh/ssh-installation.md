# Install and start the SSH server

The OpenSSH server is not installed on your Ubuntu VM. You need to install the SSH server before you can use it for remote connections.

Here’s how you can install and start the SSH server:

#### 1. Install OpenSSH Server: Run the following command to install the OpenSSH server:

```
sudo apt update
sudo apt install openssh-server
```

#### 2. Start the SSH Service: Once installed, start the SSH service with:

```
sudo systemctl start ssh
```

#### 3. Enable SSH to Start on Boot: To ensure the SSH server starts automatically when the system boots, enable it:

```
sudo systemctl enable ssh
```

#### 4. Check SSH Service Status: After starting the service, you can verify its status by running:

```
sudo systemctl status ssh
```

#### 5. Verify SSH Connectivity: After installation, you should be able to connect to the VM using its IP address.