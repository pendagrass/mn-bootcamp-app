# XSS Review Notes

Name: Pendagrass
Date: 4 November 2026

## Finding 1: Reflected XSS in the /search route

- Where untrusted data enters: the q value in the web address (req.query.q)
- Where it is output: written into the page by res.send
- Why it is dangerous: An attacker could craft a malicious URL that executes JavaScript when a victim visits the page. This could lead to session theft, unauthorised actions, data exposure, or page manipulation
- Fix applied: Updated the /search route to validate user input and safely encode the search query before displaying it in the HTML response. This prevents user input from being interpreted as executable HTML or JavaScript.
- Defence layers used: validation on input / encoding on output / CSP in the browser
Input validation: Checked and restricted the search query to acceptable input.
Output encoding: Encoded special HTML characters before inserting user input into the page.
Content Security Policy (CSP): Added browser security restrictions to reduce the risk of unauthorised script execution.
- How I retested: Submitted normal search queries to confirm the search functionality still worked.
Tested the search parameter with XSS payloads such as <script>alert('XSS')</script>.
Checked that the payload was displayed as harmless text rather than executed as JavaScript.
Inspected the browser's developer tools to confirm that the CSP was being applied.
Repeated the tests with different malicious inputs to verify that the vulnerability had been addressed.
## What SonarQube for IDE said about /search

## One thing I would check in the next app I review
