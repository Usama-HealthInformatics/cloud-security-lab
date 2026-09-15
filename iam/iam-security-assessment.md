# Cloud IAM Security Assessment

## Purpose

Identity and Access Management (IAM) controls determine who can access cloud resources and what actions they are authorized to perform.

This assessment documents defensive IAM practices for reducing unauthorized access and excessive permissions.

## 1. Least Privilege

Users, applications, and services should receive only the permissions required to perform their authorized functions.

### Security Risk

Excessive permissions can increase the impact of compromised credentials.

### Recommended Controls

* Grant only required permissions.
* Avoid unnecessary administrative privileges.
* Review permissions regularly.
* Remove unused access.
* Separate administrative and standard accounts.

---

## 2. Multi-Factor Authentication

Strong authentication should be required for sensitive accounts, particularly privileged identities.

### Recommended Controls

* Enable MFA for privileged users.
* Protect authentication factors.
* Avoid shared administrator accounts.
* Monitor authentication events.
* Require stronger authentication for sensitive operations.

---

## 3. Privileged Access

Administrative privileges should be tightly controlled.

### Security Risks

Excessive administrative access can allow an attacker to:

* Modify security settings
* Access sensitive data
* Create accounts
* Disable monitoring
* Change infrastructure
* Delete resources

### Recommended Controls

* Minimize administrator accounts.
* Use role-based access.
* Separate administrative duties.
* Review privileged permissions.
* Monitor privileged activity.

---

## 4. Service Accounts

Applications and cloud services may require identities to access other resources.

### Security Risks

Poorly managed service accounts may create persistent access paths.

### Recommended Controls

* Use dedicated service identities.
* Grant minimum required permissions.
* Avoid embedded credentials.
* Rotate credentials where applicable.
* Monitor service-account activity.
* Remove unused identities.

---

## 5. Access Reviews

IAM permissions should be reviewed periodically.

### Review Questions

* Does the user still require access?
* Are permissions appropriate?
* Is administrative access necessary?
* Are there inactive accounts?
* Are service identities still required?
* Are permissions broader than necessary?

---

## 6. Separation of Duties

Sensitive operations should not depend on a single unrestricted identity.

Example:

```text id="j9m4zf"
Developer
   |
   +---- Application Access

Security Analyst
   |
   +---- Security Monitoring

Cloud Administrator
   |
   +---- Infrastructure Management

Data Administrator
   |
   +---- Data Management
```

Separating responsibilities can reduce the impact of a compromised account and limit unauthorized changes.

---

## 7. IAM Risk Assessment

| Risk                        | Severity | Recommended Control           |
| --------------------------- | -------- | ----------------------------- |
| Excessive permissions       | High     | Least privilege               |
| Missing MFA                 | High     | Strong authentication         |
| Uncontrolled admin accounts | Critical | Privileged access management  |
| Inactive accounts           | Medium   | Periodic access review        |
| Shared credentials          | High     | Individual identities         |
| Unused service accounts     | Medium   | Identity lifecycle management |

## 8. IAM Security Checklist

* [ ] MFA enabled for privileged identities
* [ ] Least-privilege permissions implemented
* [ ] Administrative access restricted
* [ ] Individual user accounts used
* [ ] Shared credentials avoided
* [ ] Service identities reviewed
* [ ] Inactive accounts removed
* [ ] Access reviewed periodically
* [ ] Privileged activity monitored
* [ ] Security events logged

## 9. Recommended IAM Lifecycle

```text id="m8p2qd"
Create Identity
      ↓
Assign Minimum Required Access
      ↓
Authenticate
      ↓
Monitor Activity
      ↓
Review Permissions
      ↓
Modify / Revoke Access
      ↓
Remove Identity When No Longer Required
```

## Assessment Conclusion

Strong IAM controls reduce the likelihood and potential impact of unauthorized cloud access.

The most important controls are least privilege, strong authentication, controlled administrative access, identity lifecycle management, and continuous monitoring.

This assessment is a defensive cloud-security reference and does not claim configuration of a production cloud environment.
