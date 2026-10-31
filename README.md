# External Perimeter Security Assessment

A redacted portfolio case study based on an authorized client engagement completed on 31 October 2026. Client name, domain, and IP address have been omitted.

## Overview

Nmap TCP service discovery and version enumeration were combined with an OpenVAS vulnerability scan. The assessment identified internet-facing FTP, HTTP, HTTPS, MariaDB, and SSH services. OpenVAS retained two findings after filtering: FTP cleartext login (Medium, CVSS 4.8) and TCP timestamp information disclosure (Low, CVSS 2.6).

## Priority actions

1. Require encrypted FTP authentication or replace FTP with an approved secure file transfer method.
2. Restrict database access to required application and administration networks.
3. Limit SSH access to trusted sources and confirm the provider's current package and security fixes.
4. Review whether TCP timestamps are needed and disable them where appropriate.
5. Investigate the Nmap web-script errors/timeouts and validate version-based SSH CVE matches against vendor advisories.

## Evidence and limitations

The OpenVAS export reported 36 results before filtering and displayed two results meeting its minimum Quality of Detection of 70%. It therefore does not represent all scan output. Nmap's SSH CVE list is a version-based match, not confirmation that each vulnerability is present; package backports and provider builds need validation. Some web checks failed or timed out. No exploitation or authenticated configuration review is represented in this case study.

See [assessment.pdf](assessment.pdf) for the visual report. This portfolio version omits client identifiers. Share only where engagement terms permit portfolio use.
