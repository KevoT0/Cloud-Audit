# Secure Virtual Network Access Management Policy

## **Purpose**
The goal of this project is to secure access to virtual machines (VMs) in a cloud network by enforcing **least-privilege access** and ensuring only authorized users or groups can interact with these VMs. The policy follows **Cloud Control Matrix (CCM)** standards to strengthen security.

## **Scope**
This policy applies to all virtual machines within the network and ensures compliance with the **Cloud Security Alliance's Cloud Control Matrix (CCM)** for access management and auditing.

---

## **Access Control Rules**

### 1. Finance Group Access
- **Allowed:** Finance group members (Luke, Jan, Kevin)
- **Permissions:** Read, Write, Execute on VM1 (if applicable)
- **Compliance:** CCM IAM-03: Least Privilege Access

### 2. HR Group Access
- **Allowed:** HR group members (Jan, Kevin, John)
- **Permissions:** Read, Write, Execute on VM2 (if applicable)
- **Compliance:** CCM IAM-03: Least Privilege Access

### 3. IT Group Access
- **Allowed:** IT group members (Luke, Mark, Kevin)
- **Permissions:** Full Control on all VMs
- **Compliance:** CCM IAM-04: Secure Administration

### 4. Individual User Access (Exceptions)
- **Allowed/Deny:** Based on specific needs
- **Permissions:** As required on specific VMs
- **Compliance:** CCM IAM-06: User Access Reviews

### 5. Deny All Other Access
- **Denied:** All other users or groups not listed
- **Compliance:** CCM IAM-02: Access Management Policy

---

## **Cloud Audit & Compliance Questions**

### General Questions:
1. **VM List in Network?**  
   **Answer:**  
   ![VM List in Network](https://i.imgur.com/JZ6xVS0.png)  
   *Example of virtual machines in the network.*

2. **Current Access Control Mechanisms?**  
   **Answer:** None

3. **Exceptions to Access Control Rules?**  
   **Answer:** No

4. **How are User Accounts Managed?**  
   **Answer:** Managed through **Azure Active Directory**  
   ![Azure AD](https://i.imgur.com/565f0Rv.png)  
   *User and group management in Azure Active Directory*

### Policy Questions:
5. **Finance Group Members (Luke, Jan, Kevin)?**  
   **Answer:** Yes, but there’s an unauthorized user.

6. **HR Group Members (Jan, Kevin, John)?**  
   **Answer:** Yes

7. **Does IT Group Have Full Control on All VMs?**  
   **Answer:** No, Mark is missing from the group.

8. **Exceptions for Individual User Access?**  
   **Answer:** No, no documented exceptions.

### Least Privilege Questions:
9. **How are Permissions Managed?**  
   **Answer:** Some unauthorized access found in Finance group.

10. **Regular Permission Reviews?**  
    **Answer:** No

11. **Mechanisms to Prevent Unauthorized Access?**  
    **Answer:** None

### Auditing & Monitoring Questions:
12. **Logs for User Activity on VMs?**  
    **Answer:** No

13. **How Are Logs Analyzed?**  
    **Answer:** No monitoring

14. **Automated Tools for Enforcement?**  
    **Answer:** No

### Remediation Questions:
15. **What to Do for Policy Violations?**  
    **Answer:** Continuous monitoring and audits recommended.

16. **How Are Access Control Changes Approved?**  
    **Answer:** No process in place for change approval.

---

## **Recommendations**

- **Implement Role-Based Access Control (RBAC):** Enforce least-privilege access for users (**IAM-03**).
- **Conduct Regular Audits:** Review user permissions regularly (**IAM-06**).
- **Enable Logging & Monitoring:** Track activity and detect any unauthorized access (**LOG-01**).
- **Use Automated Enforcement Tools:** Help prevent unauthorized access (**IAM-02**).
- **Establish Approval Process for Changes:** Ensure all access control changes are approved (**CCC-03**).

---

## **Implementation References**
- **Cloud Security Alliance (CSA) Cloud Control Matrix (CCM)** - Refer to IAM, LOG, and CCC domains for standards.
- **Azure Active Directory RBAC Best Practices** - Use these best practices for managing user roles and permissions.

---

## **Visuals & Screenshots**
Here are some visuals that help clarify the access management implementation:

![VM List in Network](https://i.imgur.com/JZ6xVS0.png)  
*Virtual Machines within the specified network*

![Azure AD](https://i.imgur.com/565f0Rv.png)  
*User and group management in Azure Active Directory*

---

