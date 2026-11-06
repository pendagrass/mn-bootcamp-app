# Secure Development Checklist

Name: Lopezy
Date: 2 November 2026

## 1. Pipeline map

| Stage | Security activity | Example tool | Gate (what blocks progress) |
| --- | --- | --- | --- |
| Plan | Write security requirements and assess risk | Checklist, gap analysis | Requirements approved |
| Design | Threat modelling | STRIDE | Top threats have countermeasures |
| Code | Scan while you type and peer review | SonarQube for IDE, Snyk IDE plugin | No hard-coded secrets, pull request reviewed |
| Build | SAST, SCA and secrets scan | Snyk, Dependency-Check | No new High or Critical findings |
| Test | Security tests and DAST | OWASP ZAP, penetration test | No open High findings |
| Deploy | Harden configuration and protect secrets | Security headers, secrets manager | Configuration checklist signed off |
| Operate | Monitor, patch and audit | Dependabot, logs, scheduled scans | Critical patches within agreed time |

## 2. My own additions (one more security activity for each stage)

- Plan: Identify security risks and define security requirements early
- Design: Apply secure design principles to prevent vulnerabilities
- Code: Follow secure coding practices to avoid common security flaws
- Build: Scan dependencies for known security vulnerabilities.
- Test: Perform penetration testing to identify security weaknesses
- Deploy: Secure deployment configurations and protect sensitive credentials
- Operate:  Continuously monitor systems for threats and suspicious activities

## 3. My pass or fail rules for three gates

1. Gate: Build. Rule: the build fails if Snyk reports any High or Critical issue.
2. Gate:
3. Gate:

## 4. SonarQube for IDE warnings I saw in app.js
This framework implicitLy discloses version information by dedault. make sure it is safe here.

Improper input validation exposed sensitive data/information from the database to an unauthorised user/client/agent

Solution: Proper input validation (by design) to prevent unauthorised data exposure
- 
The open total issues were 65 where 13 was high, 21 medium and 31 low.