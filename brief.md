
Version: NAFATH-V1
Track: Networking

## Overview
A national digital login service requires several IT fields to work together to provide secure and reliable access to government services. Software standards define how citizens authenticate and how applications receive authorization to access protected resources. Artificial intelligence can help identify suspicious login patterns, but its decisions must be tested and monitored for accuracy, bias, and privacy risks. Mobile development ensures that the login application requests only necessary permissions and respects users' choices. Networking technologies support secure communication and reliable name resolution between users and government platforms. Cybersecurity protects accounts against phishing and unauthorized access through strong authentication methods. Finally, data governance ensures that citizens' personal information is collected, stored, and processed according to applicable legal requirements. Together, these areas help build a trustworthy, accessible, and maintainable digital identity service.
## Software
OAuth 2.0 is an authorization framework that allows applications to access protected resources with a user's permission, without sharing the user's password with each application. OpenID Connect (OIDC) builds on OAuth 2.0 by adding an identity layer for user authentication. It uses an ID Token to provide information about the authenticated user. For the national login service, OIDC is designed for user login, while OAuth 2.0 supports delegated access to resources.

Resource: OpenID Connect Core 1.0 - https://openid.net/specs/openid-connect-core-1_0.html
## AI
The NIST AI Risk Management Framework identifies four key functions: Govern, Map, Measure, and Manage. Before deploying a suspicious-login detection model, the authority should assess privacy risks, inaccurate predictions, bias, security vulnerabilities, and potential harm to legitimate users. It should test performance using representative data, monitor false positives and false negatives, document decisions, and establish human review and incident-response procedures. Continuous monitoring is necessary because attack patterns and user behaviour can change.

Resource: NIST AI Risk Management Framework - https://www.nist.gov/itl/ai-risk-management-framework
## Mobile
Android's runtime permission model requires apps to request certain sensitive permissions when they are needed, rather than automatically granting access at installation. For example, a login app should request camera access only if it provides a feature that needs the camera. The app should explain why access is needed, respect the user's decision, and handle denial gracefully. Runtime permissions reduce unnecessary access, but they do not replace secure application design or other privacy protections.

Resource: Request runtime permissions - https://developer.android.com/training/permissions/requesting
## Networking
DNS over HTTPS (DoH) sends DNS queries and responses over HTTPS, protecting their confidentiality and integrity while they travel between the client and the DNS resolver. This can prevent observers on a local network from easily reading or altering DNS messages. However, DoH does not encrypt all internet traffic, hide the user's IP address from every party, or guarantee anonymity. The protection also depends on trusting the chosen DNS resolver.

Resource: RFC 8484: DNS Queries over HTTPS - https://www.rfc-editor.org/rfc/rfc8484.html
## Cybersecurity
Phishing-resistant authentication prevents an attacker posing as a legitimate login service from reusing authentication information to access an account. NIST identifies cryptographic methods with verifier or channel binding, such as FIDO2 passkeys with user verification and appropriately configured security keys, as phishing-resistant. Passwords, SMS codes, and manually entered one-time passwords are not phishing-resistant, even when used as part of multi-factor authentication. The authority should offer phishing-resistant options to protect citizens' accounts.

Resource: NIST SP 800-63B: Authentication and Authenticator Management - https://pages.nist.gov/800-63-4/sp800-63b/authenticators/
## Data
Oman's Personal Data Protection Law and Executive Regulation establish duties for entities that process personal data, while state administrative units are addressed by a separate government data-protection policy. Relevant safeguards include informing people about processing purposes, protecting stored data, enabling applicable data-subject rights, maintaining processing records, and reporting certain breaches. The authority should confirm which rules apply to its legal status and obtain required permits for sensitive data before processing.

Resource: Personal Data Protection - Ministry of Transport, Communications and Information Technology - https://mtcit.gov.om/sectors/governance/personal
## Misconception in My Track
A common misconception is that enabling DNS over HTTPS (DoH) makes all internet activity private and anonymous. RFC 8484 defines DoH as a method for sending DNS queries and receiving responses over HTTPS; it does not claim to encrypt all subsequent application traffic or hide a user's IP address. DoH protects DNS messages in transit, but websites, service providers, and the selected DNS resolver may still observe information depending on the connection and configuration. Therefore, DoH is one privacy measure, not a complete anonymity solution.

Resource reference: RFC 8484, Section 1 — Introduction.
## Open Question
How should the authority select and monitor a trusted DoH resolver while balancing privacy, availability, logging requirements, and compliance with applicable Omani policies?
