# GitHub Authentication 
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 15-01-2024 | 16-01-2024   |         v1     |     Shantanu    |
***

# Table of Content 
1. Introduction
2. Authentication Methods
3. Comparision of Authentication Methods
4. Conclusion
5. Contact Information
6. References
***

# Introduction
GitHub Authentication is a fundamental aspect of securing and managing access to your GitHub account and projects. It encompasses a range of methods to different contexts, ensuring a secure and collaborative coding experience across various platforms. To keep account secure, one must authenticate before they can access resources on GitHub. When anyone authenticate to GitHub, they supply or confirm credentials that are unique to them to prove that they are exactly who they declare to be using different credentials depending on where they authenticate.

One can access  resources in GitHub in a variety of ways like, in the browser, with the API, or via the command line. Each way of accessing GitHub supports different modes of authentication like username and password with two-factor authentication, or a passkey, personal access token and SSH key.
***

# Authentication Methods

| Method | Description  | Required for |
| ---- | ------------- | ------------- |
| Username and password only  | Additional verification for unrecognized devices like new browser profiles or computers. | Initial sign-in from unrecognized devices (without 2FA enabled). |
| Two-factor authentication (2FA) | Requires a time-based one-time password (TOTP) from a mobile app or SMS after entering username and password. | Initial sign-in from unrecognized devices. |
| Passkey (opt-in beta) | Single-step authentication combining password and 2FA. | Initial sign-in from unrecognized devices.|
| SAML single sign-on | Necessary for accessing resources in an organization or enterprise account that uses SAML single sign-on. | Accessing resources owned by an organization using SAML single sign-on. |
| Session cookies | GitHub typically marks a user session for deletion after two weeks of inactivity. | To reload the session. |
| Authenticating to the API with a personal access token | For personal use of the GitHub REST API. Recommends fine-grained personal access tokens over classic ones. | GitHub REST API for personal use. |
| Authenticating to the API with an app | Use a GitHub App or OAuth app to access the REST API on behalf of an organization or another user. | Accessing the GitHub REST API on behalf of organizations or other users. |
| Authenticating to the API in a GitHub Actions workflow | Use the built-in GITHUB_TOKEN in a GitHub Actions workflow instead of creating a token. | Authenticating in a GitHub Actions workflow. |
| HTTPS | Authenticate with GitHub CLI using a personal access token or via the web browser. | Command line interactions with GitHub using CLI. |
| SSH | GitHub CLI finds and prompts to upload existing SSH public keys. Generates new keys if not found. | Command line interactions with GitHub using CLI. |

***
# Comparision of Authentication Methods
| Method | Ease of Setup	 | Security Level	 | Usability | Granularity of Access Control	|  Integration Complexity	 |  Multi-Factor Authentication (MFA)	 |
| ---- | ------------- | -------- | -------- | ---------- | ---------- | ---------- |
| Username and Password | Easy | Low | High |  Limited |  N/A	 |  Optional (password-based)	 |
| Personal Access Token (PAT)	 |  Moderate |  Medium to High | Moderate | High | Moderate |  Optional (token-based)	|
| SSH Keys	 |  Moderate	 |  High |  Moderate |  High |  Moderate to High	 |  Optional (key-based)	 |
| OAuth Apps	|  Moderate | Medium | High | High |  Moderate to High  | Optional (token-based)	 |
| GitHub App Installation Token	 |  Moderate |  High |  Moderate |  High  | Moderate to High	 |  Optional (token-based)	 |
| Single Sign-On (SSO)	 | Moderate to Complex	 |  High | High | High | Moderate to Complex	 |  Optional (depends on SSO provider)	 | 
***

# Setup & Use SSO
Setting up Single Sign-On (SSO) in GitHub involves using an identity provider (IdP) that supports SAML (Security Assertion Markup Language) or OAuth. Common identity providers include Okta, Azure AD, OneLogin, and others. 
**Prerequisites:**


# Conclusion

GitHub authentication plays a pivotal role in securing user accounts and ensuring the integrity of collaborative software development. GitHub provides multiple authentication mechanisms, including the traditional username-password pair, Personal Access Tokens (PATs), and SSH keys. Considering the evolving landscape of security and usability, a robust recommendation for GitHub authentication is to adopt a combination of Two-factor authentication (2FA) and Personal Access Tokens (PATs). Below are strong points for choosing this combination method:

### Two-factor authentication (2FA)
* Enhances security by requiring an additional verification step.
* Guards against unauthorized access, especially on new or unrecognized devices.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/eadad218-707b-412d-8f1e-e2f23b769896)

### Personal access token
* Provides fine-grained control over API access.
* Suitable for developers and automation processes.
* Allows secure access without exposing the primary account password.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/fbc45d22-1e73-4308-8ec9-599da6b3aabd)

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |
# References
| Source | Description  | 
| -------- | ------- | 
| https://docs.github.com/en/authentication)https://docs.github.com/en/authentication | Authentication |

