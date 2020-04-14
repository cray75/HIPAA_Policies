# 1. Introduction

Consensus Networks LLC ("Consensus Netowkrs") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As providers of compliant, hosted infrastructure used by health technology vendors, developers, designers, agencies, custom development shops, and enterprises, Consensus Networks strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by Consensus Networks to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for Consensus Networks Customers.

Consensus Networks provides secure and compliant cloud-based software for use in healthcare, specifically the HealthNet Platform. HealthNet is cited throughout policies as Customers in each category inherit different policies, procedures, and obligations from Consensus Networks.

## 1.1 HealthNet

HealthNet Customers utilize hosted software and infrastructure from Datica to deploy, host, and scale custom developed applications and configured databases. These customers are deployed into compliant containers run on systems secured and managed by Consensus Networks. Consensus Networks does not have insight or access into application level data of HealthNet Customers and, as such, does not have the ability to secure or manage risk associated with application level vulnerabilities and security weaknesses. Consensus Networks makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of HealthNet Customer data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, Snort throughout the Platform, etc).

## 1.2 Compliance Inheritance

Consensus Networks provides compliant hosted software infrastructure for its Customers. Consensus Networks's service offerings are available on AWS

Consensus Networks signs business associate agreements (BAAs) with its Customers. These BAAs outline Consensus Networks obligations and Customer obligations, as well as liability in the case of a breach. In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, Consensus Networks manages various aspects of compliance for Customers. The aspects of compliance that Consensus Networks manages for Customers are inherited by Customers, and Consensus Networks assumes the risk associated with those aspects of compliance. In doing so, Consensus Networks helps Customers achieve and maintain compliance, as well as mitigates Customers' risk.

Consensus Networks does not act as a covered entity. When Consensus Networks does operate as a business associate (not a subcontractor), Consensus Networks does not interface with users to obtain or provide access to ePHI. Access to ePHI is through our customers' applications.

Certain aspects of compliance cannot be inherited. Because of this, Consensus Networks Customers, in order to achieve full compliance or HITRUST Certification, must implement certain organizational policies. These policies and aspects of compliance fall outside of the services and obligations of Consensus Networks.

Mappings of HIPAA Rules to Consensus Networks controls and a mapping of what Rules are inherited by Customers, are covered in [§2](#2.-hipaa-inheritance).

## 1.3 Datica Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS). The network components and supporting network infrastructure are contained within the AWS infrastructures and managed by AWS. Consensus Networks does not have physical access into the network components. The Consensus Networks HealthNet environment consists of Cisco firewalls; nginx web servers; Java, Python, and Go application servers; Percona and PostgreSQL database servers; Logstash logging servers; Linux Ubuntu monitoring servers; Windows Server virtual machines; Ansible configuration management servers; Snort IDS services; Docker containers; and developer tool servers running on Linux Ubuntu.

Within the Consensus Networks HealthNet on AWS, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. Consensus Networks assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

In the case of HealthNet Customers, it is the responsibility of the Customer to restrict, secure, and assure the privacy of all ePHI data at the Application Level, as this is not under the control or purview of Consensus Networks.

The data and network segmentation mechanism differs depending on the primitives offered by the underlying cloud provider infrastructure:

* Within AWS, hosted load balancers segment data across dedicated Virtual Private Clouds for HealthNet Customers.

The segmentation strategies employed by Consensus Networks effectively create RFC 1918, or dedicated, private segmented and separated networks and IP spaces, for each HealthNet Customer.

Additionally, UFW is used on each server for logical segmentation. UFW is configured to restrict access to only justified ports and protocols. Consensus Networks has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over a TLS encrypted session.

In the case of Platform Add-ons, once the data is received from the application server, a series of Application Programming Interface (API) calls is made to the database servers where the ePHI resides. The ePHI is separated into PostgreSQL and Percona databases through programming logic built so that access to one database server will not present you with the full ePHI spectrum.

The VPN server, nginx web server, and application servers are externally facing and accessible via the Internet. The database servers, where the ePHI resides, are located on the internal Consensus Networks HealthNet network and can only be accessed through a bastion host over a VPN connection. Access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business-justified reason. Remote access to internal servers is not accessible except through load balancers.

All Platform Add-ons and operating systems are tested end-to-end for usability, security, and impact prior to deployment to production.

## 1.4 Requesting Audit and Compliance Reports

Consensus Networks, at its sole discretion, shares audit reports, including its HITRUST reports and Corrective Action Plans (CAPs), with customers on a case by case basis. All audit reports are shared under explicit NDA in Consensus Networks format between Consensus Networks and party to receive materials. Audit reports can be requested by Cosnensus Networks workforce members for Customers or directly by HealthNet Customers.

The following process is used to request audit reports:

1. Email is sent to info@datica.com. In the email, please specify the type of report being requested and any required timelines for the report.
2. Consensus Networks staff will log an issue with the details of the request into the Consensus Networks Quality Management System. The Consnesus Networks Quality Management System is used to track requests' status and outcomes.
3. Consensus Networks will confirm if a current NDA is in place with the party requesting the audit report. If there is no NDA in place, Consensus Networks will send one for execution.
4. Once it has been confirmed that an NDA is executed, Consensus Networks staff will move the issue to "Under Review".
5. The Consensus Networks Security Officer or Privacy Officer must Approve or Reject the Issue. If the Issue is rejected, Datica will notify the requesting party that we cannot share the requested report.
6. If the issue has been Approved, Datica will send the customer the requested audit report and complete the Quality Management System issue for the request.

## 1.5 Version Control

Refer to the GitHub repository at [https://github.com/catalyzeio/policies/](https://github.com/catalyzeio/policies/) for the full version history of these policies.
