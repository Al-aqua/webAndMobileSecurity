# **Lab Manual: Codacy Dashboard Practice**

**Objective**: Learn to integrate Codacy with a repository, analyze code, and resolve security/code quality issues.

---

## **Prerequisites**:

1. A **GitHub/GitLab account** (free tier).
1. A sample repository (e.g., [OWASP Juice Shop](https://github.com/juice-shop/juice-shop)).
1. A **Codacy account** ([sign up here](https://www.codacy.com/)).

---

## **Lab Setup**

1. **Create a Codacy Account**:
   - Sign up using your GitHub/GitLab credentials.
1. **Connect Codacy to Your Git Provider**:
   - Go to **Settings → Git Providers** and authorize Codacy.
1. **Add a Repository**:
   - Click **Add Repository** and select your sample repo.

---

## **Task 1: Integrate Codacy with Your Repository**

1. **Enable Codacy Checks**:
   - In Codacy, navigate to your repository’s dashboard.
   - Follow prompts to add a `.codacy.yml` file (or use default settings).
1. **Trigger Initial Analysis**:
   - Codacy will automatically scan the repository.
   - Wait for the dashboard to populate with results.

---

## **Task 2: Analyze Code Quality & Security**

1. **Explore the Codacy Dashboard**:
   - **Security Issues**: Navigate to the **Security** tab.
     - Identify vulnerabilities (e.g., hardcoded secrets, SQLi).
   - **Code Quality**: Check the **Code Patterns** tab.
     - Review code duplication, complexity, and style issues.
1. **Prioritize Issues**:
   - Filter by severity (Critical, High, Medium).
   - Click an issue to see its location in the code and remediation steps.

---

## **Task 3: Fixing Issues**

1. **Fix Issues**:

   - Click an issue to see its location in the code.
   - Understand the issue and its remediation steps.
   - Make the necessary changes to resolve the issue.

1. **Commit Changes**:

   - Push fixes to your repository.
   - Codacy will re-scan and update the dashboard.

---

## **Task 4: Review Automated Feedback**

1. **Check Pull Requests**:
   - Create a test PR in your repository.
   - Codacy will comment on the PR with new issues (if any).
1. **Verify Dashboard Updates**:
   - Return to the Codacy dashboard to see reduced issues.

## **Task 5: Additional Practice**

- Explore additional features of Codacy.
- Review the [Codacy Documentation](https://docs.codacy.com/).
- Read the [OWASP Juice Shop Official companion guide](https://leanpub.com/juice-shop)
- See if codacy found all the issues in the OWASP Juice Shop repository.
