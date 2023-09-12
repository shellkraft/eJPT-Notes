### SCAP 

**Security Content Automation Protocol Tools**
The SCAP Compliance Checker is an automated compliance scanning tool that leverages the DISA Security Technical Implementation Guidelines (STIGs) and operating system (OS) specific baselines to analyze and report on the security configuration of an information system.
### STIG

**Security Technical Implementation Guide**
STIGs are a set of cybersecurity guidelines and recommendations created by the U.S. Department of Defense (DoD) to secure computer systems and software. STIGs provide detailed instructions for configuring and securing various technologies, including operating systems, databases, and applications.

*SCAP tools often leverage STIGs to automate the assessment and remediation of security configurations on systems.*

### Using STIG viewer 

1. SCAP scan is complete and we generated a report.
2. Open STIG viewer, click on `import`
3. Click `XCCDF Result files`
4. Find and import the XML result file.

### What is Group Policy ?

Group Policy **allows administrators to define security policies for users and for computers**.

### What is a Group Policy Object (GPO)?

It is a group of settings that are created using the Microsoft Management Console (MMC) Group Policy Editor.

### What is LGPO ?

- **LGPO**- Local Group Policy Object Utility

- LGPO.exe is **a command-line utility that is designed to help automate management of Local Group** **Policy**. It can be used to import Group Policies Objects. 
### Command to apply policies using LGPO

```
LGPO.exe /g <policy-ID>
```

*CMD must be opened as an administrator in order to apply a Group Policy.*