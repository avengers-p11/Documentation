
# Authentication & Authorization

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Pravesh kumar      | 05-12-24      | Pravesh Kumar             | 10-12-24           | Khushi, shreya | | |     

---

1. [Introduction](#introduction)
2. [Authentication in Jenkins](#authentication-in-jtnkins)
3. [Authorization in Jenkins](#Authorization-in-Jenkins)
4. [Securing Jenkins with Authentication & Authorization](#Securing-Jenkins-with-Authentication-&-Authorization)
5. [Comparison of Authentication Methods](#Comparison-of-Authentication-Methods)
6. [Conclusion](#conclusion)
7. [Contact Information](#contact-information)
8. [References](#references)

---

## Introduction

Authentication and Authorization are essential components of Jenkins security, ensuring secure access and proper role-based permissions for users.

---
## Authentication in Jenkins

### What is Authentication

Authentication in Jenkins verifies the identity of users, ensuring only authorized individuals can access the system.

### Why Authentication

Authentication is crucial to prevent unauthorized access and protect sensitive data.

---
## Authentication Methods in Jenkins
### Built-in Authentication

1. Default User Database
- Jenkins maintains its own database for user authentication.
- Admin can create, delete, or manage user accounts.
- Suitable for small teams or simple setups.

### External Authentication Methods
#### 1. LDAP

- Integrates Jenkins with enterprise LDAP servers (e.g., Active Directory).
- Ideal for organizations with centralized user management.
- Requires configuring server details like server, root DN, and authentication credentials in Jenkins.

#### 2. Single Sign-On (SSO)

- Enables SSO through identity providers like Okta, Google, or Azure AD.
- Configured using plugins like SAML 2.0 Plugin or OIDC Plugin.
- Enhances user convenience and security by managing authentication externally.

#### 3. OAuth

- Jenkins supports OAuth via plugins to integrate with providers like GitHub, GitLab, and Google.
- Simplifies authentication for teams already using these platforms.

#### 4. Unix User Accounts

- Jenkins can authenticate against local Unix user accounts on the Jenkins server.

#### 5. Other Methods

- Plugins like Kerberos Authentication or Active Directory Plugin provide additional options.
  
### Plugins for Authentication

- Active Directory Plugin: Integrates with Microsoft Active Directory.
- SAML Plugin: Supports SAML 2.0-based identity providers.
- GitHub Authentication Plugin: Allows GitHub accounts to authenticate users.
- Keycloak Plugin: Integrates Jenkins with Keycloak for OAuth and SAML authentication.

---

## Authorization in Jenkins

### What is Authorization
Authorization controls what actions authenticated users can perform within Jenkins, based on their roles and permissions.

## Why Authorization
Authorization ensures users can only perform actions within their allowed scope, maintaining security and adhering to the principle of least privilege.

### Authorization Strategies

#### 1. Matrix-based Security

- Fine-grained control over permissions for individual users or groups.
- Permissions like Job Read, Build, Administer, etc., can be assigned to users/groups.

#### 2. Role-based Authorization Strategy

- Assign roles to users/groups with specific permissions.
- Global roles, project roles, and agent roles are defined for managing access.
- Requires installing the Role-based Authorization Strategy Plugin.

#### 3. Project-based Matrix Authorization

- Similar to Matrix-based Security but scoped to individual projects.
- Useful for managing large teams with varying project permissions.

#### 4. Logged-in Users Can Do Anything

- Grants full access to all logged-in users.
- Suitable for small teams with high trust levels.

#### 5. Anyone Can Do Anything

- No restrictions on access.
- NOT recommended for production environments.

#### 6. Custom Authorization Plugins

- Plugins like Authorize Project Plugin or GitLab Commit Status Plugin allow further customization of permissions based on specific conditions.
---

## Securing Jenkins with Authentication & Authorization

| Topic	|Details|
|-----|-----|
|Enable Security|	 Navigate to Manage Jenkins → Configure Global Security.|
|| Enable security and select appropriate authentication and authorization strategies.|
|Use External Providers|	 Use external providers for authentication to minimize local credential storage.|
|| Enforce stronger password policies and 2FA (Two-Factor Authentication).|
|Role-based Authorization	| Define clear roles and responsibilities to prevent unauthorized actions.|
|| Limit Administer permissions to a minimal set of users.|
|Audit Logs	| Regularly review Jenkins audit logs for suspicious activity.|
|| Use plugins like Audit Trail Plugin for enhanced logging.|
|Use Tokens for API Access	| Avoid hardcoding passwords in scripts.|
|| Use personal access tokens or API tokens instead.|


---

## Comparison of Authentication Methods

| Feature	|Built-in	|LDAP	|OAuth	|SAML (SSO)	|Unix Accounts|
|---|---|----|-----|-----|-----|
|Centralized Management|	No	|Yes	|Yes	|Yes|	No|
|Multi-Factor Authentication|	No|	Depends on provider	|Yes|	Yes|	No|
|Ease of Use	|Easy|	Moderate	|Easy	|Moderate	|Moderate|
|Integration Complexity	|Low	|High (requires LDAP server configuration)	|Moderate (via plugins)|	High (requires SAML plugin and setup)|	Low (uses existing Unix accounts)|
|Security	|Moderate (local credentials only)	|High (centralized authentication policies)	|High (provider-managed security policies)	|High (external identity provider security)	|Moderate (local Unix security policies)|
|Scalability|	Low	|High	|High	|High	|Low|
|User Convenience	|Basic (manual account management)|	Seamless for enterprise users	|Convenient for developers using OAuth apps	|Single-sign-on simplifies access	|Limited to Unix users on the server|
|Recommended for	|Small Teams	|Enterprises|	Developers	|Enterprises with SSO infrastructure|	Unix-Based Systems|

---

## Comparison of Authorization Strategies

| Feature	|Matrix-based Security	|Role-based Authorization	|Project-based Matrix	|Logged-in Users Can Do Anything	|Anyone Can Do Anything|
|-----|-----|-----|-----|-----|-----|
|Granularity	|High (per-user or per-group permissions)	|High (role-level permissions for groups/users)|	High (permissions scoped to individual projects)	|Low (broad permissions for all users)	|None|
|Ease of Management	|Moderate (manual permission assignment)	|Easy (assign roles once, reuse for groups/users)|	Moderate (permissions must be configured per project)	|High (minimal configuration needed)	|High (no configuration needed)|
|Scalability|	Moderate|	High|	High|	Low	|Low|
|Security	|High (fine-grained access control)|	High (customizable and role-specific)	|High (project-specific but potentially complex)|	Low (risky if team grows or changes)	|None (not secure, avoid in production)|
|Team Size Suitability	|Medium to Large Teams	|Small to Large Teams	|Large Teams with multiple project scopes|	Small, Highly Trusted Teams	Testing Environments Only|
|Integration |Complexity	|Low to Moderate	|Low|	Moderate	|Low	|None|
|Customization Flexibility	|Moderate (limited to permission granularity)	|High (custom roles for various requirements)|	High (projects can have unique configurations)|	None|	None|
|Recommended for|	Enterprises, Complex Teams	|Medium to Large Teams, Scalable Environments|	Large Teams, Multi-Project Scenarios	|Small Trusted Teams	|Non-Production Use Cases|

## Conclusion

Jenkins supports various authentication and authorization methods, including external options like LDAP, SSO, or OAuth. In our project, we use Built-in Authentication for user management and Role-based Authorization Strategy for assigning permissions based on responsibilities. Regular audits will ensure secure and efficient access control, aligning with our team size, infrastructure, and security needs.

---
# Contact Information

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Pravesh Kumar    |  pravesh.kumar611@gmail.com           | Pravesh899 |

---

# References

|[Jenkins Security Overview](https://www.jenkins.io/doc/book/security/)|
|[Jenkins Authentication Methods](https://www.jenkins.io/doc/book/security/authentication/)|
|[Jenkins Authorization Strategies](https://www.jenkins.io/doc/book/security/authorization/)|
|[Role-based Authorization Strategy Plugin](https://plugins.jenkins.io/role-strategy/)|
|[LDAP Plugin Documentation](https://plugins.jenkins.io/ldap/)|
