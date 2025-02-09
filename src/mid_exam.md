# Web and Mobile Security Mid-Term Exam

by: [Mohammad Al-aqua](https://github.com/al-aqua)

## Choose the correct answer for each question.

---

**Q1: Which statement best differentiates authentication from authorization?**

- A. Authentication verifies access rights, while authorization verifies a user’s identity.
- B. Authentication verifies a user’s identity; authorization verifies what the user can do.
- C. Authentication and authorization are the same processes with different names.
- D. Authorization happens before authentication.

---

<!-- **Q2: In an access control process, authentication is:** -->
<!---->
<!-- - A. Optional if the user is known. -->
<!-- - B. The first step where the user's identity is confirmed. -->
<!-- - C. The final step after all permissions are set. -->
<!-- - D. Not necessary if you use tokens. -->
<!---->
<!-- --- -->

**Q2: Which of the following represents a multi-factor authentication (MFA) scenario?**

- A. Using both a password and a CAPTCHA
- B. Using only a password but stored in a secure hash
- C. Using a hardware token and biometric verification
- D. Using two different passwords

---

**Q3: Which of the following is an example of "something you know" in authentication?**

- A. Smart card
- B. PIN
- C. OTP
- D. Fingerprint

---

**Q4: Which authentication factor represents "something you have"?**

- A. Security question answer
- B. Fingerprint
- C. One-Time Password (OTP)
- D. Username

---

**Q5: Biometric authentication falls under which category?**

- A. Something you have
- B. Something you know
- C. Something you are
- D. Something you do

---

**Q6: Which of the following statements about session-based authentication is true?**

- A. It does not require server-side storage.
- B. Session IDs are stored client-side only in local storage.
- C. It is vulnerable to session hijacking and requires server-side session management.
- D. It is designed for mobile apps exclusively.

---

**Q7: What is one primary advantage of token-based authentication over session-based authentication?**

- A. It stores user state on the server.
- B. It is inherently more secure against token theft.
- C. It is stateless, allowing for better scalability in distributed systems.
- D. It uses cookies exclusively for maintaining state.

---

<!-- **Q9: Credential stuffing is most closely related to which vulnerability?** -->
<!---->
<!-- - A. Broken access control -->
<!-- - B. Weak password policy -->
<!-- - C. Insecure dependency management -->
<!-- - D. SQL injection -->
<!---->
<!-- --- -->

**Q8: The Principle of Least Privilege is implemented by:**

- A. Allowing all users temporary administrative rights.
- B. Granting only the minimum necessary permissions to perform a function.
- C. Providing full access during working hours only.
- D. Randomly assigning permissions to avoid patterns.

---

**Q9: Rate limiting and lockout policies are used to help prevent which type of attack?**

- A. SQL injection
- B. Brute force attacks
- C. Cross-Site Scripting (XSS)
- D. Session hijacking

---

**Q10: To ensure secure password storage, which of the following should be used?**

- A. Storing passwords in plain text.
- B. Using unsalted hash algorithms.
- C. Salted hashes like bcrypt or Argon2.
- D. Using the same hash for all passwords.

---

**Q11: What is the recommended method to secure data in transit between a client and a server?**

- A. Use HTTP with additional server checks.
- B. Encrypt the data manually in the application code.
- C. Use HTTPS, ensuring data is transmitted over a secure transport layer.
- D. Trust that the network is secure by default.

---

<!-- **Q14: Which component in OAuth 2.0 represents the entity that stores and protects the resource?** -->
<!---->
<!-- - A. Client -->
<!-- - B. Resource Owner -->
<!-- - C. Resource Server -->
<!-- - D. Authorization Server -->
<!---->
<!-- --- -->

**Q12: One key advantage of using OAuth 2.0 is:**

- A. It completely eliminates the need for passwords.
- B. It allows third-party applications to access user data without exposing user credentials.
- C. It encrypts user data using asymmetric encryption.
- D. It provides client-side session storage.

---

**Q13: Encryption is defined as:**

- A. Converting ciphertext into plaintext.
- B. The process of converting plaintext data into unreadable ciphertext.
- C. A method to securely store passwords only.
- D. A type of access control mechanism.

---

**Q14: Which of the following correctly distinguishes between symmetric and asymmetric encryption?**

- A. Both use a single key for encryption and decryption.
- B. Symmetric encryption uses one key; asymmetric encryption uses a pair (public and private keys).
- C. Asymmetric encryption is generally faster than symmetric encryption.
- D. They are used interchangeably without differences.

---

**Q15: OpenSSL is primarily used to:**

- A. Serve as a proxy for web traffic.
- B. Generate encryption keys and manage digital certificates.
- C. Automatically deploy web applications.
- D. Scan code for vulnerabilities.

---

**Q16: Which of the following describes a digital certificate?**

- A. A file containing a user’s password in an encrypted format.
- B. A file containing a public key and identity information about the key owner.
- C. Always self-signed and used for local testing.
- D. A protocol for encrypting web communications.

---

**Q17: Which statement best describes SSL/TLS?**

- A. It is used for static code analysis.
- B. It is a protocol used to encrypt communications between a client and a server.
- C. It functions as a man-in-the-middle proxy.
- D. It is only used for file transfer applications.

---

**Q18: SSH (Secure Shell) is primarily used for:**

- A. Scanning web applications for vulnerabilities.
- B. Encrypted remote access and secure file transfers.
- C. Generating encryption keys.
- D. Automating code reviews.

---

**Q19: What is a recommended best practice for securing SSH access?**

- A. Disabling authentication to speed up connections.
- B. Using strong passwords or public key authentication and limiting access to authorized users.
- C. Allowing all IP addresses to connect to the SSH service.
- D. Relying solely on client-side encryption without any server-side measures.

---

**Q20: Codacy is best described as a tool that:**

- A. Scans network traffic for vulnerabilities.
- B. Automates code reviews for quality and security issues and supports multiple programming languages.
- C. Manages digital certificates for secure communications.
- D. Replaces penetration testing entirely.

---

**Q21: Which of the following practices reduces the risk of exposing sensitive information like API keys?**

- A. Embedding API keys directly in the source code.
- B. Storing API keys in plain text files.
- C. Using environment variables or secret management tools.
- D. Hardcoding API keys in public repositories.

---

**Q22: To prevent SQL injection vulnerabilities, you should:**

- A. Concatenate user inputs directly into SQL queries.
- B. Use parameterized queries or prepared statements.
- C. Disable user input validation.
- D. Store queries in hardcoded string literals without any modification.

---

**Q23: Which method is recommended to prevent Cross-Site Scripting (XSS)?**

- A. Rendering unsanitized user input directly in HTML.
- B. Disabling client-side validation.
- C. Using libraries such as DOMPurify to sanitize user input.
- D. Hardcoding all user-generated content.

---

**Q24: Why should outdated dependencies in a project be updated regularly?**

- A. Outdated dependencies improve performance but reduce code clarity.
- B. They may contain known vulnerabilities that attackers could exploit.
- C. They are challenging to maintain but secure by default.
- D. They allow for stronger encryption.

---

**Q25: When comparing session-based and token-based authentication, which of the following is true?**

- A. Session-based authentication is highly scalable for distributed systems.
- B. Token-based authentication stores user state server-side.
- C. Session-based authentication is more suitable for single-domain applications due to server-side session storage.
- D. Token-based authentication completely eliminates the risk of token theft.

---

**Q26: What is one of the primary purposes of OWASP ZAP’s automated scanners?**

- A. To generate encryption keys for secure communications.
- B. To crawl web applications and detect vulnerabilities such as SQL injection and XSS.
- C. To replace code reviews with static analysis.
- D. To manage digital certificates in a cloud environment.

---

**Q27: How does OWASP ZAP utilize its man-in-the-middle proxy feature?**

- A. It intercepts HTTP/HTTPS traffic between the client and the server, allowing inspection and modification of requests and responses.
- B. It encrypts traffic solely through the use of SSL/TLS certificates.
- C. It passes all traffic without any modification or inspection.
- D. It only works with unsecured HTTP connections.

---

Good job: You have completed the exam! ;)
