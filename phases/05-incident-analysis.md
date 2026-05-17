# Phase 05 – Incident Analysis and Response

## Objective

The objective of this phase is to analyze the detected security incident, assess its impact, and follow a structured response process aligned with SOC operations.

---

## Incident Overview

During monitoring activities, multiple alerts were generated indicating suspicious behavior on the Ubuntu server.

The detected events include:

* Multiple failed attempts to execute privileged commands using `sudo`
* Successful privilege escalation to root
* Creation of a new user account (`backdoor_user`)

This behavior is consistent with a potential compromise of a legitimate user account.

---

## Timeline of Events

The incident followed a clear sequence:

1. Multiple failed attempts to execute privileged commands
2. Successful privilege escalation to root
3. Creation of a new user account for persistence

This progression reflects a typical post-compromise scenario.

---

## Analysis

The repeated failed sudo attempts suggest an attempt to obtain elevated privileges through unauthorized or improper use of sudo.

After successfully obtaining root access, the user executed privileged actions and created a new account.  
This activity represents a potential persistence mechanism, allowing continued access to the system.

The combination of these events strongly suggests unauthorized use of privileges and a compromised account.

---

## Impact Assessment

If this incident occurred in a real environment, the potential impact could include:

* Full administrative control over the system
* Unauthorized access to sensitive data
* Ability to modify or disrupt system operations
* Persistence through unauthorized account creation

---

## Response Actions

At this stage, no direct remediation actions were performed.

The incident was validated and escalated according to standard SOC procedures.

In a real SOC environment, containment and remediation activities are typically handled by higher-level teams after proper validation and escalation. For this reason, an incident report was prepared and escalated to the Incident Response Team.

---

## Incident Escalation Report

A formal incident escalation report was prepared following validation of the suspicious activity.

The report summarizes:

* detected alerts
* incident timeline
* impact assessment
* indicators of compromise
* escalation details
* recommended actions

The report was prepared for escalation to the Incident Response Team.

### Report

[incident-escalation-report.pdf](../reports/incident-escalation-report.pdf)

---

## Recommendations

The following general security measures are recommended:

* Enforce strong password policies
* Restrict and monitor sudo privileges
* Monitor failed privilege escalation attempts
* Regularly audit user accounts
* Implement multi-factor authentication (MFA)
* Maintain centralized SIEM monitoring and alert correlation
* Maintain continuous log monitoring

---

## Conclusion

The SIEM successfully detected and correlated multiple suspicious events, providing clear visibility into the incident.

This phase demonstrates the importance of structured analysis, proper escalation, and coordinated response in a SOC environment.
