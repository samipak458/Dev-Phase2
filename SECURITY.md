# Security Policy

## Overview

Security is a top priority for the MazikCare D365 Finance and Operations model, especially given its use in healthcare environments where sensitive patient data (PHI - Protected Health Information) is involved.

## Supported Versions

The following versions of MazikCare are currently supported with security updates:

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Reporting a Vulnerability

**⚠️ IMPORTANT: Do NOT report security vulnerabilities through public GitHub issues.**

### How to Report

If you discover a security vulnerability, please follow these steps:

1. **Email the Security Team**
   - Send details to: security@mazikglobal.com (update with actual contact)
   - Subject: "[SECURITY] Brief description of the issue"

2. **Include the Following Information**
   - Type of vulnerability
   - Full paths of source file(s) related to the vulnerability
   - Location of the affected source code (tag/branch/commit)
   - Step-by-step instructions to reproduce the issue
   - Proof-of-concept or exploit code (if possible)
   - Impact of the vulnerability
   - Any potential mitigations you've identified

3. **What to Expect**
   - Acknowledgment of your report within 48 hours
   - Regular updates on the progress of addressing the issue
   - Credit for responsible disclosure (if desired)
   - Notification when the issue is fixed

### Response Timeline

- **Initial Response:** Within 48 hours
- **Status Update:** Every 5 business days
- **Fix Timeline:** Depends on severity (see below)

### Severity Levels

- **Critical:** Fix within 7 days
- **High:** Fix within 14 days
- **Medium:** Fix within 30 days
- **Low:** Fix in next planned release

## Security Best Practices

### For Contributors

1. **Never Commit Sensitive Data**
   - No passwords, API keys, or credentials
   - No connection strings with authentication
   - No PHI (Protected Health Information)
   - No PII (Personally Identifiable Information)
   - No customer data

2. **Code Security**
   - Validate all user inputs
   - Use parameterized queries (no string concatenation in SQL)
   - Implement proper error handling (don't expose system details)
   - Follow principle of least privilege
   - Use secure random number generation when needed
   - Avoid hardcoded secrets

3. **Authentication & Authorization**
   - Always use D365FO role-based security
   - Never bypass security checks
   - Test with different security roles
   - Document required privileges

4. **Data Handling**
   - Encrypt sensitive data at rest and in transit
   - Implement proper audit logging
   - Follow HIPAA guidelines for PHI
   - Anonymize test data
   - Use secure file handling practices

5. **Dependencies**
   - Keep dependencies up to date
   - Review third-party licenses
   - Audit new dependencies for security issues
   - Document all external libraries

### For Administrators

1. **Environment Security**
   - Use separate environments (Dev/Test/Prod)
   - Restrict access to production data
   - Enable audit logging
   - Regular security reviews
   - Monitor for suspicious activity

2. **Access Control**
   - Follow principle of least privilege
   - Regular access reviews
   - Remove access for departed users
   - Use strong authentication
   - Enable multi-factor authentication (MFA)

3. **Compliance**
   - Maintain HIPAA compliance
   - Follow organizational security policies
   - Regular compliance audits
   - Document security controls
   - Incident response plan

4. **Monitoring**
   - Enable D365FO audit logs
   - Monitor for unauthorized access
   - Review system logs regularly
   - Set up alerts for anomalies
   - Maintain audit trail

## Security Features

### Built-in Security

MazikCare leverages D365FO's security framework:

1. **Role-Based Access Control (RBAC)**
   - Predefined security roles
   - Fine-grained permissions
   - Segregation of duties
   - Privilege inheritance

2. **Data Security**
   - Record-level security
   - Field-level security
   - Extensible Data Security (XDS)
   - Data encryption support

3. **Audit Trail**
   - Database logging
   - User activity tracking
   - Change history
   - Compliance reporting

### Security Roles

The following security roles are defined in MazikCare:

- **HMBillingAdminRole** - Billing administration (high privilege)
- **HMClaimAgentRoles** - Claims processing (moderate privilege)
- **CallCenterManager/Agent** - Call center operations
- **ClinicHealthProfessional** - Healthcare provider access
- **ITAdmin** - IT administration (high privilege)
- And others (see AxSecurityRole/ directory)

⚠️ Review and audit role assignments regularly to ensure appropriate access levels.

## Compliance

### HIPAA Compliance

When using MazikCare in a HIPAA-regulated environment:

1. **Technical Safeguards**
   - Access controls implemented
   - Audit controls enabled
   - Data integrity mechanisms
   - Encryption for PHI

2. **Administrative Safeguards**
   - Security management process
   - Workforce security controls
   - Information access management
   - Security awareness training

3. **Physical Safeguards**
   - Facility access controls
   - Workstation security
   - Device and media controls

### GDPR Considerations

For organizations subject to GDPR:

1. **Data Protection**
   - Data minimization
   - Purpose limitation
   - Storage limitation
   - Right to erasure

2. **Documentation**
   - Data processing activities
   - Legal basis for processing
   - Data retention policies
   - Breach notification procedures

## Security Checklist

### Before Deployment

- [ ] Security code review completed
- [ ] Best practice checks passed
- [ ] Dependency audit completed
- [ ] No hardcoded credentials
- [ ] Security roles reviewed
- [ ] Test data is synthetic/anonymized
- [ ] Audit logging enabled
- [ ] Compliance requirements verified
- [ ] Incident response plan documented
- [ ] Security training completed

### Regular Reviews

- [ ] Quarterly access reviews
- [ ] Quarterly dependency audits
- [ ] Annual security assessments
- [ ] Regular penetration testing
- [ ] Compliance audits
- [ ] Security policy updates

## Resources

### Internal

- CONTRIBUTING.md - Security section
- THIRD-PARTY-LICENSES.md - Dependency information
- README.md - Setup and configuration

### External

- [Microsoft D365FO Security Documentation](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/sysadmin/security-architecture)
- [HIPAA Security Rule](https://www.hhs.gov/hipaa/for-professionals/security/index.html)
- [GDPR Information](https://gdpr.eu/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)

## Security Updates

Security updates and advisories will be communicated through:

- GitHub Security Advisories
- Release notes (for non-critical updates)
- Direct notification (for critical issues)
- Security mailing list (if established)

## Contact

For security-related questions or concerns:

- **Email:** security@mazikglobal.com (update with actual contact)
- **Emergency:** [Emergency contact number]
- **GPG Key:** [If using encrypted communication]

## Acknowledgments

We appreciate the security research community and will acknowledge responsible disclosure of security issues:

- Researchers will be credited in release notes (if desired)
- Public disclosure only after fix is deployed
- Coordinated disclosure timeline

---

**Last Updated:** 2024-10-08  
**Policy Version:** 1.0
