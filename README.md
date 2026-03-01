# Artemis-Financial
Repository created for Module 8, CS-305 Software Security

### Client Summary and Software Requirements
Artemis Financial is a financial consulting firm that sought to modernize its software while maintaining high security standards. The company required an update to its web application to ensure that sensitive financial data remained protected both during transmission and while stored. My primary task was to address a lack of encryption and data integrity checks in their existing software, basically refactoring the application to transition from insecure HTTP to the secure HTTPS protocol and adding a cryptographic checksum for data verification.

### Vulnerability Assessment and the Importance of Secure Coding
When identifying the software's vulnerabilities, I recognized the absence of transport layer security and the lack of a verifiable hash for data strings. Secure coding is vital because it protects user trust and prevents unauthorized data breaches that can lead to financial loss or legal penalties. For a company like Artemis Financial, software security adds value by helping them meet regulatory requirements, such as PCI DSS, which is essential for their business and reputation.

### Challenges and Helpful Insights
The most helpful part of the assessment was using the OWASP Dependency-Check tool to see how many "hidden" vulnerabilities exist in common third-party libraries. The most challenging aspect was configuring the SSL keystore and correctly mapping the classpath in the Spring Boot properties to ensure the certificate was recognized.

### Increasing Security Layers and Future Mitigation
I increased layers of security by implementing "Defense in Depth." This involved securing the transport layer using a 2048-bit RSA self-signed certificate and securing the data layer by implementing a SHA-256 hashing algorithm. In the future, I would continue to use static analysis tools like OWASP and dynamic analysis tools to identify vulnerabilities early in the development lifecycle, and apply the "Principle of Least Privilege" to determine which mitigation techniques are most effective for a specific system.

### Ensuring Functionality and Security Post-Refactoring
To ensure the application was functional and secure, I performed manual functional testing by verifying that the */hash* endpoint produced the expected 64-character hexadecimal output. I confirmed security by checking for the HTTPS lock icon in the browser and *port 8443* connectivity. To ensure no new vulnerabilities were introduced during refactoring, I ran a secondary static test using the dependency-check-maven plugin, which allowed me to identify and suppress non-applicable framework vulnerabilities while confirming the core code was clean.

### Resources and Future Coding Practices
The Java Keytool for certificate management and the Maven-based OWASP dependency scanner are tools I will certainly use in future tasks. Addititionally, creating a suppression.xml file to filter false positives is a critical professional skill for managing security reports efficiently.

### Showcasing Skills to Future Employers
I would showcase the refactored SslServerApplication.java and the accompanying security report. These demonstrate my ability to handle sensitive financial requirements, my proficiency with the Spring Boot framework, and my practical knowledge of modern cryptographic standards. It proves I can move beyond basic coding and take accountability for the security and integrity of a full-stack application.
