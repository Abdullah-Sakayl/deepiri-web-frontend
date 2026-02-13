# Security Policy

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

### Advisory Reference

Dependabot Alert #5\
Package: axios (npm)\
Affected Versions: \<= 1.13.4\
Patched Version: 1.13.5

### Summary

Axios is vulnerable to Denial of Service (DoS) via the `__proto__` key
in mergeConfig. When processing configuration objects containing
`__proto__` as an own property (for example, objects created using
JSON.parse), the application can crash with a TypeError, resulting in
complete denial of service.

This is NOT prototype pollution. The crash occurs before any prototype
assignment takes place.

### Resolution

1.  Upgrade axios to version 1.13.5 or later.
2.  Regenerate and commit updated lockfiles.
3.  Review application logic to ensure user-controlled JSON is not
    passed directly into axios configuration objects without validation.
4.  Confirm CI validation before closing the alert.

### Response Expectations

-   Initial review within 3 business days.
-   Patch deployment for supported versions within 7 business days.
-   Responsible disclosure practices will be followed if public
    reporting is required.

