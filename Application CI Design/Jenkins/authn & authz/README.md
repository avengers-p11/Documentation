
# Authentication & Authorization

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Pravesh kumar      | 05-12-24      | Pravesh Kumar             | 06-12-24           | Khushi, shreya | | |     

---

1. [Introduction](#introduction)
2. [Authentication in Jenkins](#authentication-in-jtnkins)
3. [Authorization in Jenkins](#Authorization-in-Jenkins)
4. [Securing Jenkins with Authentication & Authorization](#Securing-Jenkins-with-Authentication-Authorization)
5. [Comparison of Methods](#Comparison-of-Methods)
6. [Conclusion](#conclusion)
7. [Contact Information](#contact-information)
8. [References](#references)

---

## Introduction

Authentication and Authorization are essential components of Jenkins security, ensuring secure access and proper role-based permissions for users.

---
## Authentication in Jenkins

Authentication is the process of verifying the identity of a user. Jenkins provides multiple methods for user authentication, ranging from basic in-built solutions to integrations with external identity providers.

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

Authorization determines what actions a user can perform in Jenkins. Jenkins offers various strategies for access control.

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

## Comparison of Methods

|Feature	|Built-in|	LDAP	|OAuth	|SAML|	Unix|
|---|---|---|---|----|----|
|Centralized |Management	|No|	Yes	|Yes	|Yes	|No|
|Multi-factor Authentication|	No	|Depends	|Yes|	Yes|	No|
|Ease of Use	|Easy	|Moderate|	Easy|	Moderate|	Moderate|
|Recommended for	|Small Teams|	Enterprises|	Developers	|Enterprises	|Unix| Servers|

---
## Conclusion

Jenkins offers flexible authentication and authorization options, with external methods like LDAP, SSO, or OAuth recommended for production environments. Using a Role-based Authorization Strategy, which we will implement in our project, ensures precise access control, assigning roles to restrict or grant permissions based on responsibilities. Regular audits further help maintain security. The choice of methods ultimately depends on team size, infrastructure, and security requirements.

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
