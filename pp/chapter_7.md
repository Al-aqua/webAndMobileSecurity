---
marp: true
paginate: true
class: invert
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
---

# Mobile Security

## Chapter 7 – Web and Mobile Security Course

by: [Mr.Mohammad Al-aqua](https://github.com/Al-aqua)

---

# Overview of Mobile Security

- **Key Points:**
  - Importance of mobile security in modern applications
  - Unique challenges compared to web security
  - Focus on securing data storage and communications
  - Introduction to mobile app penetration testing

---

# Threat Landscape & Security Model

<div class="columns">
<div>

- **threat landscape:**
  - Malicious code injection.
  - Reverse engineering and unauthorized data access.
  - Risks from insecure inter-process communication, physical device loss/theft.

</div>

<div>

- **Security Model:**
  - Sandboxing and application signing.
  - Permission management systems
  - Security by design from development to deployment

</div>
</div>

---

# Platform-Specific Security: Android

- **Android Security Features:**
  - **Application Sandbox:** Isolates apps from each other
  - **Application Signing:** Ensures app integrity with developer certificates
  - **Permissions System:** Runtime permissions for sensitive resources
  - **Secure Storage:** Android Keystore, EncryptedSharedPreferences
  - **Regular Security Updates:** Delivered by Google Play and OEMs

---

# Platform-Specific Security: iOS

- **iOS Security Features:**
  - **Application Sandbox & Code Signing**: Enhances app integrity
  - **Data Protection APIs:** File-level encryption based on device lock status
  - **Keychain Services:** Secure storage of passwords and cryptographic keys
  - **Secure Enclave:** Manages cryptographic operations and biometric data
  - **App Transport Security (ATS)**: Enforces secure network connections (HTTPS)

---

# Securing Data Storage

- **Local Data Storage:**
  - Use strong encryption (e.g., AES-256) for files/databases
  - Utilize platform-specific secure storage (Android/iOS)
  - Minimize sensitive local data storage
- **Key Management:**
  - Store keys using Android Keystore / iOS Keychain

---

# Securing Communication

- **Encryption in Transit:** Encrypt data using TLS/SSL
- **Certificate Pinning:** Guards against man-in-the-middle (MITM) attacks
- **API Security:**
  - Implement secure authentication (OAuth, JWT)
  - Validate data, enforce rate limiting, and log transactions
- **Best Practices:**
  - Keep dependencies updated
  - Use secure network defaults and monitor traffic

---

# Mobile App Penetration Testing Tools

- **MobSF:** Automated framework for static & dynamic analysis (Android, iOS)
- **Drozer:** Security assessment tool for Android vulnerabilities
- **Frida:** Dynamic instrumentation toolkit for runtime analysis
- **Objection:** Built on Frida for live security testing without app modification
- **Additional Tools:** Burp Suite/OWASP ZAP for testing communication layers

---

# MobSF (Mobile Security Framework)

- **Overview:** A robust automated framework for both static and dynamic analysis of mobile applications (Android, iOS, Windows).
- **Key Features:**
  - Analyzes application binaries and source code.
  - Provides vulnerability assessment reports.
  - Supports malware analysis and reverse engineering.
- **Usage:**
  - Ideal for quick security assessments during the development lifecycle.
  - Integrates into CI/CD pipelines for continuous security monitoring.

---

# Drozer

- **Overview:** A comprehensive security assessment tool for Android applications.
- **Key Features:**
  - Helps identify vulnerabilities in Android apps.
  - Assists in simulating attack scenarios by interacting with the Android framework.
  - Provides a modular architecture allowing custom extensions.
- **Usage:**
  - Commonly used in professional penetration testing engagements.
  - Useful for exploring application vulnerabilities on real devices and emulators.

---

# Frida

- **Overview:** A dynamic instrumentation toolkit for real-time debugging and analysis.
- **Key Features:**
  - Capable of hooking into an application’s runtime on-the-fly.
  - Supports JavaScript-based scripting for custom hooks.
  - Works across Android, iOS, Windows, macOS, and Linux.
- **Usage:**
  - Ideal for reverse engineering and dynamic analysis.
  - Enables deep inspection of app behavior during execution.

---

# Objection

- **Overview:** A runtime mobile exploration toolkit built on top of Frida.
- **Key Features:**
  - Provides an easy-to-use command interface for mobile security testing.
  - Allows for bypassing jailbreak/root detection.
  - Performs live security assessments without needing to modify the app.
- **Usage:**
  - Often leveraged in mobile app pentests for rapid assessment.
  - Suitable for testers who want to evaluate security without code changes.

---

# Additional Tools (Burp Suite / OWASP ZAP)

- **Burp Suite:**
  - A popular web vulnerability scanner that can be configured as a proxy for mobile app traffic.
  - Useful for intercepting, modifying, and replaying mobile network requests.
- **OWASP ZAP:**
  - An extendable, open-source tool for web application security testing.
  - Can be configured to test mobile network communications via proxy settings.
- **Usage**
  - Ideal for testing the communication layers of mobile apps.
  - Helps identify vulnerabilities in API endpoints and HTTP/HTTPS traffic.

---

# Best Practices & Considerations

- **Secure Development Life Cycle (SDLC):** Integrate security at all stages (design, coding, testing, deployment)
- **Regular Audits & Code Reviews:** Automated tools + manual code reviews for early vulnerability detection
- **Frequent Updates:** Keep libraries, frameworks, and apps updated
- **Developer Education:** Continuous training on security best practices
- **Incident Response & Compliance:**
  - Prepare and update incident response plans
  - Adhere to regulatory requirements (GDPR, HIPAA, etc.)

---

# Links and Resources

- [MobSF](https://github.com/MobSF)
- [Drozer](https://github.com/WithSecureLabs/drozer)
- [Frida](https://frida.re/)
- [Objection](https://github.com/sensepost/objection)
- [GDPR](https://gdpr.eu/)

---

# <!--fit--> Q&A
