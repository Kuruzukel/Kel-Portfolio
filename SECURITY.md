# Security Policy

## Overview

This document outlines the security policy for the Michael D. Cruz Portfolio website. While this is a static portfolio website with minimal security risks, we take the protection of user data and system integrity seriously.

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Security Measures

### Current Implementation

1. **Static Content Delivery**
   - No server-side processing or database connections
   - Minimal attack surface due to static nature
   - Content served via HTTPS when deployed

2. **External Dependencies**
   - React 18 loaded from official CDN (unpkg.com)
   - Google Fonts loaded via official Google Fonts API
   - All external resources loaded over HTTPS

3. **Client-Side Security**
   - No storage of sensitive user data
   - No cookies or local storage implementation
   - No form submissions or data collection

4. **Content Security**
   - Personal information limited to publicly available contact details
   - PDF resume hosted locally without sensitive information
   - Images optimized and scanned for metadata

### Best Practices Implemented

- **Cross-Site Scripting (XSS) Prevention**: React's built-in XSS protection through JSX
- **External Links**: All external links use `rel="noopener noreferrer"` attributes
- **Resource Integrity**: Dependencies loaded from trusted CDN sources
- **HTTPS**: Recommended deployment over HTTPS for encrypted transmission

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please follow these steps:

### How to Report

1. **Do Not** open a public issue for security vulnerabilities
2. Send a detailed report to: **mikasaackerman.jme@gmail.com**
3. Include the following information:
   - Description of the vulnerability
   - Steps to reproduce the issue
   - Potential impact assessment
   - Suggested fix (if available)

### What to Expect

- **Initial Response**: Within 48 hours of report submission
- **Status Update**: Regular updates every 72 hours until resolution
- **Resolution Timeline**:
  - Critical vulnerabilities: 7 days
  - High severity: 14 days
  - Medium severity: 30 days
  - Low severity: 60 days

### Disclosure Policy

- Security issues will be addressed privately until a fix is deployed
- Reporter will be credited (unless anonymity is requested)
- Public disclosure will occur after fix deployment and reasonable time for users to update

## Security Considerations for Deployment

### Recommended Hosting Configuration

1. **HTTPS Enforcement**
   - Always serve content over HTTPS
   - Implement HSTS (HTTP Strict Transport Security)
   - Use valid SSL/TLS certificates

2. **HTTP Headers**

   ```
   Content-Security-Policy: default-src 'self' https://unpkg.com https://fonts.googleapis.com https://fonts.gstatic.com; script-src 'unsafe-inline' https://unpkg.com; style-src 'unsafe-inline' https://fonts.googleapis.com
   X-Content-Type-Options: nosniff
   X-Frame-Options: DENY
   X-XSS-Protection: 1; mode=block
   Referrer-Policy: strict-origin-when-cross-origin
   ```

3. **Access Control**
   - Restrict access to sensitive files (.git, configuration files)
   - Implement proper file permissions on server

### Deployment Checklist

- [ ] Enable HTTPS with valid certificate
- [ ] Configure security headers
- [ ] Remove development files and comments
- [ ] Verify all external resources use HTTPS
- [ ] Test for common vulnerabilities (XSS, CSRF, clickjacking)
- [ ] Implement rate limiting (if applicable)
- [ ] Set up monitoring and logging
- [ ] Regular dependency updates

## Known Limitations

1. **Third-Party Dependencies**
   - React loaded from CDN (unpkg.com)
   - Google Fonts loaded from external source
   - Dependency on external service availability

2. **Client-Side Rendering**
   - JavaScript required for full functionality
   - Potential for client-side manipulation (no sensitive operations)

3. **Static Nature**
   - No authentication or authorization mechanisms
   - No server-side validation
   - Limited ability to implement advanced security features

## Privacy Considerations

### Data Collection

This website does not:

- Collect personal information from visitors
- Use cookies or tracking technologies
- Store data in local storage or session storage
- Implement analytics or tracking scripts
- Process form submissions

### Third-Party Services

External resources loaded:

- **React (unpkg.com)**: JavaScript library for UI rendering
- **Google Fonts**: Typography resources

Users should review the privacy policies of these services independently.

## Updates and Maintenance

### Security Updates

- Dependencies reviewed quarterly
- Security patches applied within 7 days of disclosure
- Regular security audits performed semi-annually

### Version History

- **v1.0.0** (2025-03-22): Initial release with security policy

## Contact

For security-related inquiries:

**Michael D. Cruz**

- Email: mikasaackerman.jme@gmail.com
- Response Time: Within 48 hours

For general inquiries, please use the contact information provided on the portfolio website.

---

**Last Updated**: March 22, 2025

This security policy is subject to updates and improvements. Please check regularly for the latest version.
