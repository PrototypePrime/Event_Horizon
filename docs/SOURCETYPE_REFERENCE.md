# Event-Horizon: Sourcetype Reference Guide

This document lists all supported sourcetypes with their verification status, descriptions, and required Splunk Add-ons.

## Status Definitions

| Status | Description |
|--------|-------------|
| ✅ **Verified** | Production-ready templates approved by user & Splunk TA testing |
| 🧪 **Beta** | Functional templates under active refinement |
| 📋 **Planned** | On roadmap for future implementation |

---

## Endpoints

| Sourcetype | Status | Description | Required Add-on | Splunkbase ID |
|:-----------|:------:|:------------|:----------------|:--------------:|
| `XmlWinEventLog:Security` | ✅ Verified | Windows security events (logons, privilege use, process creation) | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `XmlWinEventLog:System` | ✅ Verified | Windows system events (service start/stop, driver load, system errors) | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `XmlWinEventLog:Sysmon` | ✅ Verified | Sysmon telemetry (process, network, file, registry activity) | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `XmlWinEventLog:PowerShell` | ✅ Verified | PowerShell script execution and command logging | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `syslog` | 🧪 Beta | Generic Unix/Linux syslog messages | Splunk Add-on for Unix and Linux | 833 |
| `linux_secure` | 🧪 Beta | Linux authentication logs (SSH, sudo, login failures) | Splunk Add-on for Unix and Linux | 833 |
| `auditd` | 🧪 Beta | Linux system call auditing (file access, syscalls, permission changes) | Splunk Add-on for Unix and Linux | 833 |
| `crowdstrike:json` | 🧪 Beta | CrowdStrike Falcon EDR detections and events | Splunk Add-on for CrowdStrike FDR | 5094 |
| `cs:falcon:event` | 🧪 Beta | CrowdStrike Falcon process and endpoint activity | Splunk Add-on for CrowdStrike FDR | 5094 |
| `sentinelone:log` | 🧪 Beta | SentinelOne EDR activity and threat intelligence | Splunk Add-on for SentinelOne | 5110 |
| `sentinelone:threat` | 🧪 Beta | SentinelOne threat detections and malware analysis | Splunk Add-on for SentinelOne | 5110 |
| `symantec:ep` | 🧪 Beta | Symantec Endpoint Protection antivirus/firewall events | Splunk Add-on for Symantec EP | 2772 |
| `symantec:ep:security` | 🧪 Beta | Symantec Endpoint Protection security logs | Splunk Add-on for Symantec EP | 2772 |
| `mdatp:event` | 🧪 Beta | Microsoft Defender ATP endpoint events and telemetry | Splunk Add-on for Microsoft Defender | N/A |
| `mdatp:alert` | 🧪 Beta | Microsoft Defender ATP alerts and threat detections | Splunk Add-on for Microsoft Defender | N/A |
| `WinEventLog:Microsoft-Windows-Windows Defender/Operational` | 🧪 Beta | Windows Defender real-time protection and scan events | Splunk Add-on for Microsoft Windows | 742 |
| `osquery:results` | 🧪 Beta | OSQuery endpoint query results | Splunk Add-on for OSQuery | N/A |

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
| `cisco:vpn` | 🧪 Beta | Cisco ASA VPN logs | [Splunk Add-on for Cisco ASA](https://splunkbase.splunk.com/app/1620) | 1620 |
| `pulse:connect` | 🧪 Beta | Pulse Connect Secure VPN logs | [Splunk Add-on for Pulse Connect Secure](https://splunkbase.splunk.com/app/4074) | 4074 |
| `pulse:secure:syslog` | 🧪 Beta | Pulse Secure Syslog | [Splunk Add-on for Pulse Connect Secure](https://splunkbase.splunk.com/app/4074) | 4074 |

---

## Cloud

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `aws:cloudtrail` | ✅ Verified | [Splunk Add-on for AWS](https://splunkbase.splunk.com/app/1876) | 1876 |
| `aws:cloudwatch:vpc_flow` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `aws:flow_logs` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `aws:s3:accesslogs` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `aws:cloudwatch:guardduty` | 🧪 Beta | Splunk Add-on for AWS | 1876 |
| `azure:activity:log` | 🧪 Beta | Azure infrastructure activity logs (NOT Azure AD - see Identity section) | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `azure:audit` | 🧪 Beta | Generic Azure audit logs (NOT Azure AD - see Identity section) | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `azure:networksecuritygroup:flow` | 🧪 Beta | Azure NSG flow logs for network traffic analysis | Splunk Add-on for Microsoft Cloud Services | 3110 |
| `vmware:esx:syslog` | 🧪 Beta | Splunk Add-on for VMware | 3215 |
| `vmware:vcenter` | 🧪 Beta | Splunk Add-on for VMware | 3215 |
| `WinEventLog:Microsoft-Windows-Hyper-V-VMMS` | 🧪 Beta | Splunk Add-on for Microsoft Hyper-V | N/A |

---

## Identity

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `OktaIM2:log` | ✅ Verified | [Splunk Add-on for Okta Identity Cloud](https://splunkbase.splunk.com/app/6553) | 6553 |
| `azure:aad:signin` | ✅ Verified | [Splunk Add-on for Microsoft Azure](https://splunkbase.splunk.com/app/3757) | 3757 |
| `azure:aad:audit` | ✅ Verified | [Splunk Add-on for Microsoft Azure](https://splunkbase.splunk.com/app/3757) | 3757 |
| `azure:aad:risk:detection` | ✅ Verified | [Splunk Add-on for Microsoft Azure](https://splunkbase.splunk.com/app/3757) | 3757 |
| `Cisco:ISE:Syslog` | ✅ Verified | [Splunk Add-on for Cisco ISE](https://splunkbase.splunk.com/app/1915) | 1915 |
| `duo:authentication` | 🧪 Beta | Splunk Add-on for Duo Security | 3393 |
| `aruba:clearpass` | 🧪 Beta | Splunk Add-on for Aruba ClearPass | 3494 |
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
| `f5:bigip:asm` | 🧪 Beta | Splunk Add-on for F5 BIG-IP | 2680 |

---

## Applications

| Sourcetype | Status | Required Add-on | Splunkbase ID |
|:-----------|:------:|:----------------|:--------------|
| `iis` | 🧪 Beta | Splunk Add-on for Microsoft IIS | 3185 |
| `ms:iis:auto` | 🧪 Beta | Splunk Add-on for Microsoft IIS | 3185 |
| `access_combined` | 🧪 Beta | Splunk Add-on for Apache Web Server | 3186 |
| `apache:access` | 🧪 Beta | Splunk Add-on for Apache Web Server | 3186 |
| `apache:error` | 🧪 Beta | Splunk Add-on for Apache Web Server | 3186 |
| `nginx:access` | 🧪 Beta | [Splunk Add-on for NGINX](https://splunkbase.splunk.com/app/3258) | 3258 |
| `ms:o365:reporting:messagetrace` | 🧪 Beta | [Splunk Add-on for Microsoft Office 365](https://splunkbase.splunk.com/app/4055) | 4055 |
| `o365:management:activity` | 🧪 Beta | [Splunk Add-on for Microsoft Office 365](https://splunkbase.splunk.com/app/4055) | 4055 |
| `proofpoint_tap_siem` | ✅ Verified | Proofpoint TAP threat intelligence (phishing, malware, BEC detections) | [Splunk Add-on for Proofpoint TAP](https://splunkbase.splunk.com/app/3822) | 3822 |
| `mimecastsiemst` | ✅ Verified | Mimecast email security (spam, TTP, impersonation, delivery logs) | [Mimecast for Splunk](https://splunkbase.splunk.com/app/4075) | 4075 |
| `zscalerlss-zpa-app` | ✅ Verified | Zscaler Private Access application logs (app access, blocked attempts) | [TA-Zscaler_CIM](https://splunkbase.splunk.com/app/3865) | 3865 |
| `zscalerlss-zpa-audit` | ✅ Verified | Zscaler ZPA configuration audit (policy changes, user actions) | [TA-Zscaler_CIM](https://splunkbase.splunk.com/app/3865) | 3865 |
| `zscalerlss-zpa-auth` | ✅ Verified | Zscaler ZPA authentication (login success/failure, session events) | [TA-Zscaler_CIM](https://splunkbase.splunk.com/app/3865) | 3865 |
| `zscalerlss-zpa-bba` | ✅ Verified | Zscaler ZPA Browser Access (HTTP/HTTPS traffic, web requests) | [TA-Zscaler_CIM](https://splunkbase.splunk.com/app/3865) | 3865 |
| `zscaler:web` | 🧪 Beta | Zscaler Internet Access (ZIA) web logs | [Splunk Add-on for Zscaler](https://splunkbase.splunk.com/app/2763) | 2763 |
| `zscaler:lss` | 🧪 Beta | Zscaler Nanolog Streaming Service (LSS) | [Splunk Add-on for Zscaler](https://splunkbase.splunk.com/app/2763) | 2763 |
| `bluecoat:proxysg:main` | 🧪 Beta | Blue Coat ProxySG main access logs | [Splunk Add-on for Blue Coat ProxySG](https://splunkbase.splunk.com/app/1792) | 1792 |
| `bluecoat:proxysg:access` | 🧪 Beta | Blue Coat ProxySG access logs | [Splunk Add-on for Blue Coat ProxySG](https://splunkbase.splunk.com/app/1792) | 1792 |
| `mcafee:webgateway:access` | 🧪 Beta | McAfee Web Gateway access logs | [Splunk Add-on for McAfee Web Gateway](https://splunkbase.splunk.com/app/1926) | 1926 |
| `mcafee:wg` | 🧪 Beta | McAfee Web Gateway main logs | [Splunk Add-on for McAfee Web Gateway](https://splunkbase.splunk.com/app/1926) | 1926 |
| `proofpoint:tap:message` | ✅ Verified | Proofpoint TAP message log (Alias) | [Splunk Add-on for Proofpoint TAP](https://splunkbase.splunk.com/app/3822) | 3822 |
| `mimecast:siem` | ✅ Verified | Mimecast SIEM log (Alias) | [Mimecast for Splunk](https://splunkbase.splunk.com/app/4075) | 4075 |
| `infoblox:dns` | 🧪 Beta | Infoblox DNS queries and replies | [Splunk Add-on for Infoblox](https://splunkbase.splunk.com/app/2912) | 2912 |
| `infoblox:dhcp` | 🧪 Beta | Infoblox DHCP leases and messages | [Splunk Add-on for Infoblox](https://splunkbase.splunk.com/app/2912) | 2912 |
| `cisco:ios:dhcp` | 🧪 Beta | Cisco IOS DHCP events | [Splunk Add-on for Cisco Catalyst](https://splunkbase.splunk.com/app/7538) | 7538 |
| `dhcp` | 🧪 Beta | Windows DHCP Server logs | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `WinEventLog:Dhcp-Server` | 🧪 Beta | Windows DHCP Server logs (Verbose) | [Splunk Add-on for Microsoft Windows](https://splunkbase.splunk.com/app/742) | 742 |
| `WinEventLog:DNS-Server` | 🧪 Beta | Windows DNS Server logs | [Splunk Add-on for Microsoft Windows DNS](https://splunkbase.splunk.com/app/3666) | 3666 |
| `MS_DNS_Server` | 🧪 Beta | Windows DNS Server debug logs | [Splunk Add-on for Microsoft Windows DNS](https://splunkbase.splunk.com/app/3666) | 3666 |

...

## Summary

| Category | Total | Verified | Beta |
|:---------|------:|:--------:|:----:|
| Endpoints | 17 | 4 | 13 |
| Network | 19 | 10 | 9 |
| Cloud | 12 | 2 | 10 |
| Identity | 10 | 5 | 5 |
| Security | 9 | 0 | 9 |
| Applications | 41 | 5 | 36 |
| **Total** | **108** | **26** | **82** |

---

## Contributing

To request a new sourcetype or report template issues, please [open an issue on GitHub](https://github.com/PrototypePrime/Event_Horizon/issues).

---

**[⬅ Back to README](../README.md)**
