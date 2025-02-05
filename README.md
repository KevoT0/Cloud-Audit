# Secure Virtual Network Access Management Policy

## Purpose
- Enforce least-privilege access to virtual machines (VMs) within the virtual network.
- Ensure only authorized users and groups can access and interact with the VMs.
- Align access control mechanisms with **Cloud Control Matrix (CCM)** standards to enhance security posture.

## Scope
- Applies to all virtual machines within the specified virtual network.
- Ensures compliance with Cloud Security Alliance (CSA) **Cloud Control Matrix (CCM)** access management and auditing controls.

## Access Control Rules

### 1. Finance Group Access
- **Action:** Allow  
- **Resources:** VM1 (if applicable)  
- **Users/Groups:** Finance group (Luke, Jan, and Kevin)  
- **Permissions:** Read, Write, Execute  
- **CCM Reference:** IAM-03: Least Privilege Access

### 2. HR Group Access
- **Action:** Allow  
- **Resources:** VM2 (if applicable)  
- **Users/Groups:** HR group (Jan, Kevin, John)  
- **Permissions:** Read, Write, Execute  
- **CCM Reference:** IAM-03: Least Privilege Access

### 3. IT Group Access
- **Action:** Allow  
- **Resources:** All VMs  
- **Users/Groups:** IT group (Luke, Mark, Kevin)  
- **Permissions:** Full Control (or specified permissions as required)  
- **CCM Reference:** IAM-04: Secure Administration

### 4. Individual User Access (Exceptions)
- **Action:** Allow/Deny (based on specific needs)  
- **Resources:** Specific VMs  
- **Users:** Individual users (e.g., Sam)  
- **Permissions:** As required  
- **CCM Reference:** IAM-06: User Access Reviews

### 5. Deny All Other Access
- **Action:** Deny  
- **Resources:** All VMs  
- **Users/Groups:** All other users and groups not explicitly defined in the above rules.  
- **CCM Reference:** IAM-02: Access Management Policy

---

## Cloud Audit

### General Questions
1. Can you provide a list of all virtual machines within the specified virtual network?  
   **Answer:**
<p align="center">
<img src="https://i.imgur.com/JZ6xVS0.png" height="80%" width="80%" alt="Endpoint vulnerabilities"/>

2. What are the current access control mechanisms in place for these virtual machines?  
   **Answer:** None  

3. Are there any documented exceptions to the "Deny All Other Access" rule in the policy?  
   **Answer:** None  
4. How are user accounts and groups managed within the organization?  
   **Answer:** Azure Active Directory  
<p align="center">
<img src="https://i.imgur.com/565f0Rv.png" height="80%" width="80%" alt="Endpoint vulnerabilities"/>

<img src="https://i.imgur.com/gySrfHw.png" height="80%" width="80%" alt="Endpoint vulnerabilities"/>

### Policy-Related Questions
5. Can you confirm that the Finance group includes users Luke, Jan, and Kevin?  
   **Answer:** Yes, but there is another user (fraudster).  

<p align="center">
<img src="https://i.imgur.com/K6i1bSh.png" height="80%" width="80%" alt="Endpoint vulnerabilities"/>
  
6. Does the HR group include users Jan, Kevin, and John?  
   **Answer:** Yes  
<p align="center">
<img src="https://i.imgur.com/mVSWZ6s.png" height="80%" width="80%" alt="Endpoint vulnerabilities"/>

7. Does the IT group (Luke, Mark, and Kevin) have Full Control on all VMs?  
   **Answer:** No, Mark is not in the group.  

<p align="center">
<img src="https://i.imgur.com/8kjlkfK.png" height="80%" width="80%" alt="Endpoint vulnerabilities"/>

8. Are there any documented justifications for individual user access exceptions?  
  **Answer:** No
### Least Privilege Questions
9. How do you ensure that users/groups receive only the necessary permissions?  
   **Answer:** No, an unknown user has access to the Finance Group.  
10. Are there regular reviews to adjust user permissions?  
    **Answer:** No  
11. What mechanisms prevent unauthorized VM access?  
    **Answer:** None  
- **CCM Reference:** IAM-06: User Access Reviews

### Auditing and Monitoring Questions
12. Are there logs tracking user activity on VMs?  
    **Answer:** No  
13. How are logs monitored and analyzed?  
    **Answer:** No  
14. Are there automated tools to enforce access control policies?  
    **Answer:** No  
- **CCM Reference:** LOG-01: Audit Logging & Monitoring

### Remediation Questions
15. What are the procedures for addressing access control policy violations?  
    **Answer:** Continuous monitoring and internal audits should be conducted regularly.  
16. How are access control changes documented and approved?  
    **Answer:** No changes have been made.  
- **CCM Reference:** CCC-03: Change Management Policy

---

## Recommendations
- Implement **role-based access control (RBAC)** to enforce least privilege (**IAM-03**).
- Conduct **regular audits** to review user permissions (**IAM-06**).
- Enable **logging and monitoring** for user activity on VMs (**LOG-01**).
- Use **automated tools** to detect and prevent unauthorized access (**IAM-02**).
- Establish **a formal approval process** for access control changes (**CCC-03**).

---

### Implementation References
- **Cloud Security Alliance (CSA) Cloud Control Matrix (CCM)** - IAM, LOG, CCC domains
- **Azure Active Directory Role-Based Access Control (RBAC) Best Practices**
---
