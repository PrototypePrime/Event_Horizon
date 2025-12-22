# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 2.1.x   | :white_check_mark: |
| 2.0.x   | :white_check_mark: |
| < 2.0   | :x:                |

## Reporting a Vulnerability

If you discover a security vulnerability in Event-Horizon, please report it responsibly.

### How to Report

1. **Do NOT open a public issue** for security vulnerabilities
2. Contact the maintainer directly via [LinkedIn](https://www.linkedin.com/in/mathan-subbiah-0bb47aa8/)
3. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if any)

### What to Expect

- **Acknowledgment:** Within 48 hours
- **Initial Assessment:** Within 7 days
- **Resolution Timeline:** Depends on severity

### Scope

This policy applies to:
- The Event-Horizon Docker image
- The Event-Horizon source code
- Official documentation

### Out of Scope

- Third-party dependencies (report to their maintainers)
- Issues in user-generated log content
- Self-hosted instances with custom modifications

## Security Best Practices

When using Event-Horizon:

1. **Isolate from Production:** Run in dedicated test environments
2. **Secure HEC Tokens:** Don't commit tokens to repositories
3. **Network Isolation:** Limit access to the UI in shared environments
4. **Review AI Output:** AI-generated content should be reviewed before use

---

Thank you for helping keep Event-Horizon secure! 🔒
