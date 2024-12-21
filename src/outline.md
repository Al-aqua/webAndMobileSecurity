## Course Outline: Web and Mobile Security

### **1. Introduction to Web and Mobile Security**

- Overview of web and mobile security
- Common vulnerabilities and threats (e.g., OWASP Top 10, mobile-specific risks)
- Setting up the environment: Tools and technologies

______________________________________________________________________

### **2. Web Browser Developer Tools**

- Overview of web browser developer tools (Chrome DevTools, Firefox Developer Tools)
- Inspecting and analyzing HTML, CSS, and JavaScript
- Debugging network requests and responses
- Identifying potential security issues (e.g., insecure cookies, mixed content, CORS)

______________________________________________________________________

### **3. Authentication and Authorization**

#### **3.1. Pure PHP Implementation**

- Understanding authentication vs. authorization
- Building secure login and registration systems
- Hashing passwords using `password_hash()` and `password_verify()`
- Implementing role-based access control (RBAC)
- Protecting sessions and mitigating session hijacking

#### **3.2. Laravel Implementation**

- Laravel authentication basics (using `auth` scaffolding)
- Customizing authentication workflows
- Implementing authorization policies and gates
- Securing APIs with Passport or Sanctum
- Best practices in Laravel security

______________________________________________________________________

### **4. Secure Communication**

#### **4.1. OpenSSL**

- Introduction to encryption and digital certificates
- Generating public and private keys
- Encrypting and decrypting data using OpenSSL
- Securing web communications with SSL/TLS

#### **4.2. SSH (Secure Shell)**

- Basics of SSH and its use in secure communication
- Generating and managing SSH keys
- Configuring SSH for secure remote access
- Mitigating common SSH vulnerabilities

______________________________________________________________________

### **5. Secure Code Analysis**

#### **5.1. Codacy**

- Overview of Codacy as a code quality and security analysis tool
- Integrating Codacy with GitHub/GitLab
- Identifying and resolving code vulnerabilities
- Continuous improvement through automated code reviews

______________________________________________________________________

### **6. Web Application Vulnerability Scanning**

#### **6.1. OWASP ZAP**

- Introduction to OWASP ZAP (Zed Attack Proxy)
- Setting up and configuring OWASP ZAP
- Scanning web applications for vulnerabilities
- Understanding and mitigating identified risks
- Integrating OWASP ZAP into CI/CD pipelines

______________________________________________________________________

### **7. Mobile Security**

- Overview of mobile app security principles
- Understanding platform-specific security features (Android/iOS)
- Securing data storage and communication in mobile apps
- Introduction to mobile app penetration testing tools

______________________________________________________________________

### **8. Capstone Project**

- Students will build a secure web or mobile application.
- Key deliverables:
  - Authentication and authorization system
  - Secure communication using OpenSSL and/or SSH
  - Secure coding practices integrated with Codacy
  - Application vulnerability scanning using OWASP ZAP
- Students will document vulnerabilities found and mitigated during development.

______________________________________________________________________

### **9. Practical Mid-Term and Final Exam**

- Mid-Term: Hands-on tasks covering PHP, Laravel, and OpenSSL.
- Final Exam: Comprehensive practical tasks integrating all course modules.

______________________________________________________________________

### **Optional Topics (Time Permitting)**

- Introduction to penetration testing frameworks (e.g., Metasploit)
- Introduction to API security (JWT, OAuth2)
- Overview of content security policies (CSP)
