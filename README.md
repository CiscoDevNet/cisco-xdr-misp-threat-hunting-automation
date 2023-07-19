![License: CISCO](https://img.shields.io/badge/License-CISCO-blue.svg)
[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://developer.cisco.com/codeexchange/github/repo/CiscoDevNet/cisco-xdr-misp-threat-hunting-automation)

# MISP Events to Cisco XDR Incident and Ticketing System

## Features
*	Import events from [MISP](https://www.circl.lu/doc/misp/automation/) into Cisco XDR.
*	Automatically enrich observables and search for potential compromised assets with an automated Cisco XDR Investigation.
*	Send observables judgements to Private intel database within Cisco XDR and connect this feed to your security solutions (e.g. Cisco Sure Firewall). 
*	Auto create a prioritized and correlated incident within Cisco XDR Incident Manager, combing all sightings per MISP event in 1 single Incident.
*	Post Incident to a ticketing system or notification of choice (this can Webex, Email, MS teams, ServiceNow etc.).

> **Note:** Please test this properly before implementing in a production environment. This is a sample workflow!

## Required Targets
- MISP API ([Automation Remote Connector](https://docs.xdr.us.security.cisco.com/Content/Automate/options-remotes.htm) may be needed)

## Required Account Keys
- [MISP API Keys](https://www.circl.lu/doc/misp/automation/)

## Setup instructions

### Configure Global Variables

1. Browse to your Cisco XDR orchestration instance. This wille be a different URL depending on the region your account is in: 

* US: https://xdr.us.security.cisco.com/automate/workflows
* EU: https://xdr.eu.security.cisco.com/automate/workflows
* APJC: https://xdr.apjc.security.cisco.com/automate/workflows

2. Click on **IMPORT** to import the workflow:

3. Click on **Browse** and copy paste the content of the [misp-event-to-incident-workflow.json](https://raw.githubusercontent.com/CiscoDevNet/cisco-xdr-misp-threat-hunting-automation/main/misp-event-to-incident-workflow.json) file inside of the text window. Select **IMPORT AS A NEW WORKFLOW (DUPLICATE)** and click on **IMPORT**.

4. When importing the workflow, you will be prompted for missing information, click **UPDATE**, then click **CONTINUE** for the Target selection as they are prefilled.
5. After this you will be prompted for the MISP Token, please fill in your "Automation Key" here that you have retrieved from [MISP](https://www.circl.lu/doc/misp/automation/#automation-key). This key will be stored encrypted as Secure String. After filling this in your can click **IMPORT**.

6. As final step, please click on the first block in the workflow, named **GET Events From MISP**. Make sure you have filled in the MISP HTTP Target in the Target selection. There is a pre-built Target which you can edit by clicking on the pencil icon, named "MISP HTTP Target". Again, please note that if the MISP Server is in your internal network, you will need a [Automation Remote Connector](https://docs.xdr.us.security.cisco.com/Content/Automate/options-remotes.htm).

7. At the bottom of the Workflow you can optionally add any ticketing system or notification of choice.

## Notes

* Please test this properly before implementing in a production environment. This is a sample workflow!

## Author(s)

* Pieter van Schaik (Cisco)
* Maarten Lutterman (Cisco)
* Christopher van der Made (Cisco)
