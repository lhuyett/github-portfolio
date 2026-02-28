# 1. ZTA Component Definitions

* Policy Engine (PE)
The Policy Engine is the decision maker of the Zero Trust Architecture. It determines whether access should or shouldn't be granted by evaluating all of the security signals like identity, device health, location, and risk factor. 

* Policy Administrator (PA)
The Policy Administrator acts as the rule distributor and session controller. It takes the decisions from the PE and turns it into instructions. If access is approved then it establishes the connection and gives config instructions to the PEP. If access was denied then it makes sure the connection is blocked. 

* Policy Enforcement Point (PEP)
THe Policy Enforcement Point is the gatekeeper that actually givers access or blocks it to the resource. It sits in front of the protected system and enforces whatever decision the PE gives it. 

# 2. ZT Core Principle (Verify Explicitly)

For the Verify Explicitly Zero Trust principle it requires that every access request is to be evaluated using multiple security signals before access is granted. 

For the Golden State Water Treatment Facility’s HR Employee PII Database, the Policy Engine enforces Verify Explicitly by evaluating:
* The User's Identity
* If the device is compliant and up to date
* If the request is coming from an approved location

An example is that if an HR manager attempts to access background check records then the policy engine will verify that the user successfully completed the multi factor authentication, the device is encrypted and has the updated security patches, and the request originated from the secure VPN or on site. 

If anything fails in this process then the PE will deny access. 

# 3. Policy Table

| Policy Requirement (Signal) | Condition to be Met by User | Action if Condition is Met |
|-----------------------------|-----------------------------|----------------------------|
| User Identity | User must authenticate using company credentials with Multi-Factor Authentication. | Grant Access |
| Device Posture | Device must be encrypted, running current security patches, and have active endpoint protection enabled. | Grant Access |
| Network Context | Access request must originate hrough the facility’s approved VPN connection. | Grant Access |

---
Project: Lab 6 - Zero Trust Policy

Filename: ZT-Policy-Profile.md

Commit Message: Added Zero Trust Policy Profile for Golden State Water Treatment Facility HR PII Database - https://github.com/lhuyett/github-portfolio/Lab-02/ZT-Policy-Profile.md 

Due Date: Feb 27, 2026
---