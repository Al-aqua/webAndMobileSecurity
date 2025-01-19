# Lab Manual: Chapter 4 - Secure Communication

## **Chapter Overview**

In this chapter, students will learn about secure communication techniques using OpenSSL and SSH. The goal is to understand encryption, digital certificates, and secure remote access. Students will perform hands-on exercises to generate keys, encrypt/decrypt data, and configure secure communication channels.

______________________________________________________________________

## **Lab Objectives**

By the end of this lab, students will:

1. Understand the basics of encryption and secure communication.
1. Generate and manage public/private key pairs using OpenSSL and SSH.
1. Encrypt and decrypt data using OpenSSL.
1. Configure and use SSH for secure remote access.
1. Mitigate common vulnerabilities in secure communication.

______________________________________________________________________

## **Lab Prerequisites**

- A computer with Linux (Ubuntu/Debian preferred) or macOS. Windows users can use WSL (Windows Subsystem for Linux) or a virtual machine.
- OpenSSL installed (pre-installed on most Linux/macOS systems).
- SSH client and server installed (e.g., `openssh-client` and `openssh-server`).
- Basic knowledge of the Linux command line.

______________________________________________________________________

## **Lab 4.1: OpenSSL**

### **Step 1: Generating Public and Private Keys**

1. Open a terminal.

1. Generate a private key using the RSA algorithm:

   ```bash
   openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
   ```

   - **Explanation**: This command generates a 2048-bit RSA private key and saves it to `private_key.pem`.

1. Extract the public key from the private key:

   ```bash
   openssl rsa -pubout -in private_key.pem -out public_key.pem
   ```

   - **Explanation**: This command extracts the public key and saves it to `public_key.pem`.

1. Verify the contents of the keys:

   ```bash
   cat private_key.pem
   cat public_key.pem
   ```

______________________________________________________________________

### **Step 2: Encrypting and Decrypting Data**

1. Create a sample text file to encrypt:

   ```bash
   echo "This is a secret message" > message.txt
   ```

1. Encrypt the file using the public key:

   ```bash
   openssl pkeyutl -encrypt -inkey public_key.pem -pubin -in message.txt -out encrypted_message.bin
   ```

   - **Explanation**: This command encrypts `message.txt` using the public key and saves the encrypted data to `encrypted_message.bin`.

1. Decrypt the file using the private key:

   ```bash
   openssl pkeyutl -decrypt -inkey private_key.pem -in encrypted_message.bin -out decrypted_message.txt
   ```

   - **Explanation**: This command decrypts `encrypted_message.bin` using the private key and saves the decrypted data to `decrypted_message.txt`.

1. Verify the decrypted message:

   ```bash
   cat decrypted_message.txt
   ```

______________________________________________________________________

### **Step 3: Securing Web Communications with SSL/TLS**

1. Generate a self-signed SSL certificate:

   ```bash
   openssl req -x509 -newkey rsa:2048 -keyout server_key.pem -out server_cert.pem -days 365 -nodes
   ```

   - **Explanation**: This command generates a self-signed SSL certificate (`server_cert.pem`) and a private key (`server_key.pem`) valid for 365 days.

1. Inspect the certificate:

   ```bash
   openssl x509 -in server_cert.pem -text -noout
   ```

1. Use the certificate and key in a web server (e.g., Apache or Nginx) to enable HTTPS (optional, for advanced students).

______________________________________________________________________

### **Exercise 1: OpenSSL Practice**

1. Generate a 4096-bit RSA key pair.
1. Encrypt a file named `student_data.txt` using the public key.
1. Decrypt the file using the private key and verify the contents.
1. Generate a self-signed certificate valid for 2 years and inspect its details.

______________________________________________________________________

## **Lab 4.2: SSH (Secure Shell)**

### **Step 1: Generating SSH Keys**

1. Generate an SSH key pair:

   ```bash
   ssh-keygen -t rsa -b 2048 -f ~/.ssh/id_rsa
   ```

   - **Explanation**: This command generates a 2048-bit RSA key pair and saves it to `~/.ssh/id_rsa` (private key) and `~/.ssh/id_rsa.pub` (public key).

1. View the generated keys:

   ```bash
   cat ~/.ssh/id_rsa
   cat ~/.ssh/id_rsa.pub
   ```

______________________________________________________________________

### **Step 2: Configuring SSH for Secure Remote Access**

1. Copy the public key to a remote server:

   ```bash
   ssh-copy-id user@remote_server_ip
   ```

   - Replace `user` with the username and `remote_server_ip` with the server's IP address.

1. Test passwordless SSH login:

   ```bash
   ssh user@remote_server_ip
   ```

1. Secure the SSH server by editing the SSH configuration file:

   ```bash
   sudo nano /etc/ssh/sshd_config
   ```

   - Disable root login:
     ```
     PermitRootLogin no
     ```
   - Allow only specific users:
     ```
     AllowUsers your_username
     ```
   - Save and restart the SSH service:
     ```bash
     sudo systemctl restart ssh
     ```

______________________________________________________________________

### **Step 3: Mitigating Common SSH Vulnerabilities**

1. Enable key-based authentication and disable password authentication:

   - Edit the SSH configuration file:
     ```bash
     sudo nano /etc/ssh/sshd_config
     ```
   - Set the following:
     ```
     PasswordAuthentication no
     PubkeyAuthentication yes
     ```
   - Save and restart the SSH service:
     ```bash
     sudo systemctl restart ssh
     ```

______________________________________________________________________

### **Exercise 2: SSH Practice**

1. Generate an SSH key pair and copy the public key to a remote server.
1. Configure the SSH server to:
   - Disable root login.
   - Allow only key-based authentication.
1. Test the configuration by logging in to the server.

______________________________________________________________________

## **Additional Challenge**

Set up a simple web server (e.g., using Python's `http.server`) and secure it with the self-signed SSL certificate generated in Lab 4.1.
