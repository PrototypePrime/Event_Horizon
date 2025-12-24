# Event-Horizon: Sourcetype Reference Guide

This document lists all supported sourcetypes with their verification status and required Splunk Add-ons.

## Status Definitions

| Status | Description |
|--------|-------------|
| ✅ **Verified** | Production-ready templates approved by user & Splunk TA testing |
| 🧪 **Beta** | Functional templates under active refinement |
| 📋 **Planned** | On roadmap for future implementation |

---

## Endpoints

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `XmlWinEventLog:Security` | ✅ Verified | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `XmlWinEventLog:System` | ✅ Verified | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `XmlWinEventLog:Sysmon` | ✅ Verified | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `XmlWinEventLog:PowerShell` | ✅ Verified | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `syslog` | 🧪 Beta | Splunk Add-on for Unix and Linux | 833 |
| `linux_secure` | 🧪 Beta | Splunk Add-on for Unix and Linux | 833 |
| `auditd` | 🧪 Beta | Splunk Add-on for Unix and Linux | 833 |
| `crowdstrike:json` | 🧪 Beta | Splunk Add-on for CrowdStrike FDR | 5094 |
| `cs:falcon:event` | 🧪 Beta | Splunk Add-on for CrowdStrike FDR | 5094 |
| `sentinelone:log` | 🧪 Beta | Splunk Add-on for SentinelOne | 5110 |
| `sentinelone:threat` | 🧪 Beta | Splunk Add-on for SentinelOne | 5110 |
| `symantec:ep` | 🧪 Beta | Splunk Add-on for Symantec EP | 2772 |
| `symantec:ep:security` | 🧪 Beta | Splunk Add-on for Symantec EP | 2772 |
| `mdatp:event` | 🧪 Beta | Splunk Add-on for Microsoft Defender | N/A |
| `mdatp:alert` | 🧪 Beta | Splunk Add-on for Microsoft Defender | N/A |
| `WinEventLog:Microsoft-Windows-Windows Defender/Operational` | 🧪 Beta | Splunk Add-on for Microsoft Defender | N/A |
| `osquery:results` | 🧪 Beta | Splunk Add-on for OSQuery | N/A |

---

## Network

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `pan:traffic` | ✅ Verified | [Splunk Add-on for Palo Alto Networks](https://splunkbase.splunk.com/app/2757) | 2757 |
| `pan:threat` | ✅ Verified | [Splunk Add-on for Palo Alto Networks](https://splunkbase.splunk.com/app/2757) | 2757 |
| `pan:system` | ✅ Verified | [Splunk Add-on for Palo Alto Networks](https://splunkbase.splunk.com/app/2757) | 2757 |
| `cisco:ios` | ✅ Verified | [Splunk Add-on for Cisco Catalyst](https://splunkbase.splunk.com/app/7538) | 7538 |
| `cisco:asa` | ✅ Verified | [Splunk Add-on for Cisco ASA](https://splunkbase.splunk.com/app/1620) | 1620 |
| `cisco:firepower:syslog` | ✅ Verified | [CCX Unified Add-on for Cisco Firepower](https://splunkbase.splunk.com/app/4785) | 4785 |
| `fortigate_traffic` | ✅ Verified | [Splunk Add-on for Fortinet FortiGate](https://splunkbase.splunk.com/app/2846) | 2846 |
| `fortigate_event` | ✅ Verified | [Splunk Add-on for Fortinet FortiGate](https://splunkbase.splunk.com/app/2846) | 2846 |
| `fortigate_utm` | ✅ Verified | [Splunk Add-on for Fortinet FortiGate](https://splunkbase.splunk.com/app/2846) | 2846 |
| `juniper:junos` | 🧪 Beta | Splunk Add-on for Juniper | 2845 |
| `juniper:junos:firewall` | 🧪 Beta | Splunk Add-on for Juniper | 2845 |
| `f5:bigip:ltm` | 🧪 Beta | Splunk Add-on for F5 BIG-IP | 2680 |
| `f5:bigip:asm` | 🧪 Beta | Splunk Add-on for F5 BIG-IP | 2680 |
| `cisco:syslog` | 🧪 Beta | Splunk Add-on for Cisco Catalyst | 7538 |
| `citrix:netscaler:syslog` | 🧪 Beta | Splunk Add-on for Citrix NetScaler | 2770 |
| `stream:dns` | 🧪 Beta | Splunk Stream | 1809 |
| `stream:http` | 🧪 Beta | Splunk Stream | 1809 |

---

## Cloud

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `aws:cloudtrail` | ✅ Verified | [Splunk Add-on for AWS](https://splunkbase.splunk.com/app/1876) | 1876 |
| `aws:cloudwatch:vpc_flow` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `aws:flow_logs` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `aws:s3:accesslogs` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `aws:cloudwatch:guardduty` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `azure:activity:log` | 🧪 Beta | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `azure:audit` | 🧪 Beta | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `azure:networksecuritygroup:flow` | 🧪 Beta | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `vmware:esx:syslog` | 🧪 Beta | Splunk Add-on for VMware | 3215 |
| `vmware:vcenter` | 🧪 Beta | Splunk Add-on for VMware | 3215 |
| `WinEventLog:Microsoft-Windows-Hyper-V-VMMS` | 🧪 Beta | Splunk Add-on for Microsoft Hyper-V | N/A |

---

## Identity

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `okta:im` | 🧪 Beta | Splunk Add-on for Okta | 2806 |
| `okta:system` | 🧪 Beta | Splunk Add-on for Okta | 2806 |
| `azure:aad:signin` | 🧪 Beta | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `azure:aad:audit` | 🧪 Beta | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `Cisco:ISE:Syslog` | ✅ Verified | [Splunk Add-on for Cisco ISE](https://splunkbase.splunk.com/app/1915) | 1915 |
| `duo:authentication` | 🧪 Beta | Splunk Add-on for Duo Security | 3393 |
| `mssql:audit` | 🧪 Beta | Splunk Add-on for Microsoft SQL Server | 5631 |
| `oracle:audit:xml` | 🧪 Beta | Splunk Add-on for Oracle | 1910 |
| `oracle:syslog` | 🧪 Beta | Splunk Add-on for Oracle | 1910 |

---

## Security

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `akamai:siem` | 🧪 Beta | Akamai SIEM Integration | 4310 |
| `cloudflare:json` | 🧪 Beta | Splunk Add-on for Cloudflare | N/A |
| `nessus:scan` | 🧪 Beta | Splunk Add-on for Tenable | 3057 |
| `qualys:detection` | 🧪 Beta | Splunk Add-on for Qualys | 2964 |
| `qualys:scan` | 🧪 Beta | Splunk Add-on for Qualys | 2964 |
| `akamai:cm:json` | 🧪 Beta | Splunk Add-on for Akamai | N/A |
| `cloudflare:firewall` | 🧪 Beta | Splunk Add-on for Cloudflare | N/A |
| `nessus:plugin` | 🧪 Beta | Splunk Add-on for Tenable | 3057 |

---

## Applications

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `iis` | 🧪 Beta | Splunk Add-on for Microsoft IIS | 3185 |
| `ms:iis:auto` | 🧪 Beta | Splunk Add-on for Microsoft IIS | 3185 |
| `access_combined` | 🧪 Beta | Splunk Add-on for Apache Web Server | 3186 |
| `apache:access` | 🧪 Beta | Splunk Add-on for Apache Web Server | 3186 |
| `apache:error` | 🧪 Beta | Splunk Add-on for Apache Web Server | 3186 |
| `nginx:access` | 🧪 Beta | Splunk Add-on for NGINX | 3258 |
| `ms:o365:reporting:messagetrace` | 🧪 Beta | Splunk Add-on for Microsoft Office 365 | 4055 |
| `o365:management:activity` | 🧪 Beta | Splunk Add-on for Microsoft Office 365 | 4055 |
| `proofpoint:tap:message` | 🧪 Beta | Splunk Add-on for Proofpoint TAP | 3822 |
| `proofpoint:tap:click` | 🧪 Beta | Splunk Add-on for Proofpoint TAP | 3822 |
| `mimecast:gateway` | 🧪 Beta | Splunk Add-on for Mimecast | 3717 |
| `mimecast:siem` | 🧪 Beta | Splunk Add-on for Mimecast | 3717 |
| `zscaler:lss` | 🧪 Beta | Splunk Add-on for Zscaler | N/A |
| `zscaler:web` | 🧪 Beta | Zscaler Technical Add-On for Splunk | 3865 |
| `infoblox:dns` | 🧪 Beta | Splunk Add-on for Infoblox | 2940 |
| `infoblox:dhcp` | 🧪 Beta | Splunk Add-on for Infoblox | 2940 |
| `WinEventLog:DNS-Server` | 🧪 Beta | Splunk Add-on for Microsoft DNS | 3632 |
| `MS_DNS_Server` | 🧪 Beta | Splunk Add-on for Microsoft DNS | 3632 |
| `dhcp` | 🧪 Beta | Splunk Add-on for ISC DHCP | N/A |
| `WinEventLog:Dhcp-Server` | 🧪 Beta | Splunk Add-on for Microsoft DHCP | N/A |
| `cisco:ios:dhcp` | 🧪 Beta | Splunk Add-on for Cisco Catalyst | 7538 |

---

## Summary

| Category | Total | Verified | Beta |
|:---------|------:|:--------:|:----:|
| Endpoints | 17 | 4 | 13 |
| Network | 14 | 9 | 5 |
| Cloud | 11 | 1 | 10 |
| Identity | 9 | 1 | 8 |
| Security | 8 | 0 | 8 |
| Applications | 21 | 0 | 21 |
| **Total** | **80** | **15** | **65** |

---

## Contributing

To request a new sourcetype or report template issues, please [open an issue on GitHub](https://github.com/PrototypePrime/Event_Horizon/issues).

---

**[⬅ Back to README](../README.md)**
