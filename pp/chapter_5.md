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

# Codacy: Automating Code Quality and Security
![bg fit right:20%](./codacy.png)
Web and Mobile Security Course

by: Mr.Mohammad Al-aqua

---

# Introduction to Codacy

* **Overview:**
  * Cloud-based automated code review tool.
  * Supports 40+ languages (Java, Python, JavaScript, etc.).
  * Combines **SAST** (Static Application Security Testing) and code quality checks.
  * Integrates with GitHub, Bitbucket, and GitLab or self-hosted Git repositories.

* **Key Features:**
  * Security vulnerability detection (e.g., SQLi, XSS).
  * Code duplication, complexity, and style enforcement.
  * Compliance with standards like OWASP Top 10.

---

# Why Codacy Matters in Security

* **Code Quality ↔ Security:**
  * Poor code quality (e.g., hardcoded secrets, misconfigurations) leads to exploits.
  * Proactive risk mitigation in CI/CD pipelines.

* **Shift-Left Security:**
  * Catch issues early in development, not post-deployment.

---

# Identifying Vulnerabilities

* **Common Security Issues Detected:**
  * Insecure dependencies (via CVE databases).
  * Broken authentication, improper error handling.
  * Secrets exposure (API keys, passwords).

* **Prioritization**
  * Severity levels (Critical, High, Medium).
  * Actionable feedback with remediation steps.

---

# Vulnerability Examples

## Hardcoded Secrets
```javascript
// Bad Practice: Hardcoded API Key
const apiKey = "12345-ABCDE-SECRET-KEY";

// Good Practice: Use environment variables
const apiKey = process.env.API_KEY;
```
**Explanation**
- Hardcoded secrets in code can be easily exposed in version control.
- Codacy flags this and suggests using environment variables or secret management tools.

---

# Vulnerability Examples (2)

## SQL Injection
```python
# Bad Practice: Vulnerable to SQL Injection
query = "SELECT * FROM users WHERE username = '" + user_input + "';"

# Good Practice: Use parameterized queries
query = "SELECT * FROM users WHERE username = %s;"
cursor.execute(query, (user_input,))
```
**Explanation**
- Directly concatenating user input into SQL queries can lead to SQL injection attacks.
- Codacy detects this and recommends using parameterized queries or ORM frameworks.
---

# Vulnerability Examples (3)

## Cross-Site Scripting (XSS)
```javascript
// Bad Practice: Unsanitized user input
var userInput = req.query.user;
var html = "<h1>Hello, " + userInput + "!</h1>";
res.send(html);

// Good Practice: Sanitize user input
var userInput = req.query.user;
var html = "<h1>Hello, " + sanitize(userInput) + "!</h1>";
res.send(html);
```
**Explanation**
- Rendering unsanitized user input in HTML can lead to XSS attacks.
- Codacy flags this and suggests using libraries like `DOMPurify` or built-in escaping functions..

---

# Vulnerability Examples (4)

## Insecure Dependency
```json
// Bad Practice: Using a vulnerable library version
{
  "dependencies": {
    "express": "4.16.0" // Known vulnerabilities in this version
  }
}
// Good Practice: Update to a secure version
{
  "dependencies": {
    "express": "4.18.2" // Latest secure version
  }
}

```
**Explanation** Outdated dependencies may contain known vulnerabilities.

---

# Resolving Issues & Best Practices

* **Workflow Example:**
  * Developer → Receives Codacy alert on PR → Fixes code → Rescan.

* **Best Practices:**
  * Use Codacy’s auto-fix suggestions for code style.
  * Regularly update tool rulesets for emerging threats.

---

# Continuous Improvement

* **Automated Code Reviews:**
  * Enforce team coding standards.
  * Track technical debt metrics over time.

* **Reporting:**
  * Security/compliance dashboards for audits.
  * Historical trends for team performance.

---

# Codacy vs. Alternatives

- **Comparison Table**:  
  | **Tool** | **Strengths** | **Weaknesses** |  
  |----------|---------------|----------------|  
  | Codacy   | Easy integration, multi-language | Limited custom rules |  
  | SonarQube | Highly customizable | Complex setup |  
  | Snyk     | Dependency-focused | Less code-style focus |  

---

# Summary & Takeaways

* Codacy bridges security and code quality in DevOps.
* Key benefits: Automation, scalability, developer-friendly feedback.
* Always complement with manual code reviews and penetration testing.

---

# Q&A + References

- Codacy Docs: [https://www.codacy.com/docs](https://docs.codacy.com/)
- OWASP Secure Coding Practices.