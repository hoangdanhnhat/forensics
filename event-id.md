# Important Windows Event IDs

This document provides a summary of critical Windows Event IDs, categorized for easier organization and monitoring of important security events. These IDs are crucial for system administrators and security professionals to audit and maintain the security posture of their environments.

***

## Logon Events

These events track user logon and logoff activities, providing visibility into who is accessing a system and when.

### Success and Failure Events

* **4624:** A user successfully logged on to a computer.
* **4625:** An attempt to log on with an unknown user name or bad password failed.
* **4634:** A user's logoff process was completed.
* **4647:** A user initiated the logoff process.
* **4648:** A user successfully logged on using explicit credentials while already logged on as a different user.

### Advanced Logon Events

* **4768:** A Kerberos authentication ticket (TGT) was requested.
* **4769:** A Kerberos service ticket was requested.
* **4779:** A user disconnected a terminal server or virtual host session without logging off.
* **4798:** A user’s local group membership was enumerated.
* **4799:** A security-enabled local group membership was enumerated.
* **4820:** A Kerberos Ticket-granting-ticket (TGT) was denied.
* **4821:** A Kerberos service ticket was denied because the user or device did not meet access control restrictions.
* **4822:** NTLM authentication failed because the account was a member of the Protected User group.
* **4823:** NTLM authentication failed because access control restrictions were required.
* **4824:** Kerberos pre-authentication using DES or RC4 failed because the account was a member of the Protected User group.
* **5379:** A security audit event in Windows that indicates a read operation was performed on credentials stored in the Windows Credential Manager.

***

## Privilege Use Events

This category covers events related to how users utilize their assigned privileges, including access to objects and system resources.

### Object Access

These events relate to access attempts on resources like files, folders, and registry keys.

* **4656:** A request to handle or access an object was made.
* **4658:** A handle to an object was closed.
* **4659:** A handle to an object was requested with the intent to delete it.
* **4660:** An object was deleted.
* **4663:** An attempt to access an object was made.
* **4664:** An attempt to create a hard link was made.
* **4670:** An object's permissions were changed.
* **4691:** Indirect access to an object was requested.

### PowerShell and Scheduled Tasks

* **4103:** PowerShell Module Logging event.
* **4104:** PowerShell Script Block Logging event.
* **4698:** A scheduled task was created.
* **4699:** A scheduled task was deleted.
* **4700:** A scheduled task was enabled.
* **4701:** A scheduled task was disabled.
* **4702:** A scheduled task was updated.

### Privilege Assignment and Use

* **4672:** Special privileges were assigned to a new logon.
* **4673:** A privileged service was called.
* **4674:** An operation was attempted on a privileged object.
* **4985:** A transaction state was changed.
* **5051:** A file was virtualized.

***

## Windows Server Events

These events are specifically relevant for monitoring the health and security of Windows Server environments, indicating potentially high-criticality events.

* **1100:** The event logging service has shut down.
* **1101:** Audit events have been dropped by the transport.
* **1102:** The audit log was cleared.
* **1104:** The security log is now full.
* **4618:** A monitored security event pattern occurred.
* **4649:** A potential replay attack was detected.
* **4719:** A change to the system audit policy was made.
* **4765:** A SID History was added to an account.
* **4766:** A failed attempt was made to add SID History to an account.
* **4794:** An attempt was made to set Directory Services Restore Mode.
* **4897:** Role separation was enabled.
* **4964:** Special groups were assigned to a new logon.
* **5124:** An update was made to the security setting on the OCSP Responder Service.

***

## Microsoft Defender Antivirus Events

These Event IDs provide insight into the activity and status of Microsoft Defender Antivirus, including malware detection and system protection actions.

* **1002:** A malware scan stopped before completion.
* **1003:** A malware scan was paused.
* **1005:** A malware scan failed.
* **1006, 1116:** Malware or unwanted software was detected.
* **1007, 1117:** An action to protect the system was performed.
* **1008, 1118:** An action to protect the system failed.
* **1009:** An item was restored from quarantine.
* **1012:** An item in quarantine could not be deleted.
* **1015:** Suspicious behavior was detected.
* **1119:** A critical error occurred while taking action.

## Others

Event IDs that I find useful.

* **325:** A new database is created by the database engine.
* **327:** A newly created database is detached by the database engine and marked ready to use.
* **7036:** A service change state ( "entered the running state" or "entered the stopped state." )
* **4, 9, 10, 300, 303:** NTFS mount and dismount events.