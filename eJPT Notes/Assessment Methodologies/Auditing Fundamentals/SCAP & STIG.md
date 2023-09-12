### SCAP 

**Security Content Automation Protocol Tools**
SCAP tools are software applications and utilities designed to automate various aspects of security management and compliance. They provide a standardized way to assess, monitor, and report on the security configuration and vulnerabilities of computer systems.

### STIG

**Security Technical Implementation Guide**
STIGs are a set of cybersecurity guidelines and recommendations created by the U.S. Department of Defense (DoD) to secure computer systems and software. STIGs provide detailed instructions for configuring and securing various technologies, including operating systems, databases, and applications.

*SCAP tools often leverage STIGs to automate the assessment and remediation of security configurations on systems.*

### Using STIG viewer 

1. SCAP scan is complete and we generated a report.
2. Open STIG viewer, click on `import`
3. Click `XCCDF Result files`
4. Find and import the XML result file.

### Using LGPO to fix the issues

- **LGPO**- Local Group Policy Object Utility

- LGPO.exe is **a command-line utility that is designed to help automate management of Local Group**. **Policy**. It can import and apply settings from Registry Policy (Registry. pol) files, security templates, Advanced Auditing backup files, as well as from formatted “LGPO text” files.

### Command to apply policies using LGPO

```
LGPO.exe /g <policy-name>
```