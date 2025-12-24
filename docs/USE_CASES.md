# 💡 Use Cases & Examples

Real-world scenarios where Event-Horizon saves hours of work.

---

> **Note:** All scenarios below are recommended for execution in **isolated test environments** or dedicated development indices to prevent data pollution in production.

---

## 1. Detection Rule Validation 🔍

**Scenario:** You wrote a new correlation rule to detect "Brute Force + Successful Login + Privilege Escalation"

**Without Event-Horizon:**
- Wait days/weeks for a real attack
- Or manually craft 100+ logs across multiple formats
- Hope you got the timing and sequence right

**With Event-Horizon:**
```bash
1. Mode: Multi (AI Auto-Discover)
2. Scenario: "Failed login attempts followed by successful admin login"
3. IOC IP: 192.0.2.100
4. Generate → Push to Dev Splunk
5. Verify your rule triggers correctly
```

**Result:** ⏱️ Days → **5 Minutes**

---

## 2. SOC Analyst Training 🎓

**Scenario:** Onboarding a new analyst, need to show them what a ransomware attack looks like in logs

**With Event-Horizon:**
```bash
1. Generate realistic "ransomware" attack logs
2. Push to training Splunk instance
3. Walk analyst through:
   ✓ Initial phishing email (cisco:esa)
   ✓ Payload execution (Sysmon)
   ✓ Lateral movement (WinEventLog:Security)
   ✓ Encryption activity (file system logs)
   ✓ C2 communication (firewall logs)
```

**Benefits:**
- ✅ Safe, repeatable environment
- ✅ Realistic attack progression
- ✅ Can replay multiple scenarios
- ✅ No risk of exposing real production data

---

## 3. Dashboard Population & Testing 📊

**Scenario:** Built a new Palo Alto firewall dashboard, but production has sparse data

**With Event-Horizon:**
```bash
1. Mode: Single
2. Sourcetype: pan:traffic
3. Count: 50,000
4. Time Range: Last 7 days (distributed evenly)
5. Generate → Push to Dev → Verify dashboards render correctly
```

**Benefits:**
- ✅ Test all dashboard panels with realistic data
- ✅ Verify drilldowns work properly
- ✅ Check for performance issues before production rollout
- ✅ Populate dev/staging environments quickly

**Real Example:**
```
Before: "This panel needs 30 days of data... let's wait"
After: Generate 100k logs for last 30 days in 2 minutes
```

---

## 4. Performance & Stress Testing ⚡

**Scenario:** Need to stress-test your Splunk indexers before Black Friday traffic spike

**With Event-Horizon:**
```bash
1. Generate 1M logs across multiple sourcetypes
2. Push to HEC at controlled rate (e.g., 10k/min)
3. Monitor:
   - Indexer CPU/Memory
   - Queue depths
   - Search performance
   - License usage
```

**Benefits:**
- ✅ Identify bottlenecks before production issues
- ✅ Validate infrastructure capacity
- ✅ Test different ingestion patterns
- ✅ Benchmark search performance

---

## 5. Multi-Vendor Correlation Testing 🔗

**Scenario:** Testing correlation across Firewall + EDR + IAM logs

**With Event-Horizon:**
```bash
Attack: "Compromised credentials used for lateral movement"

Generated Logs:
├─ WinEventLog:Security - Failed logins from compromised account
├─ pan:traffic - Unusual internal scanning
├─ crowdstrike:fdr - Suspicious process execution
└─ aws:cloudtrail - Unauthorized API calls

Result: 4 separate data sources telling one coherent story
```

**Benefits:**
- ✅ Test cross-platform correlation rules
- ✅ Verify timestamp alignment
- ✅ Check for gaps in coverage
- ✅ Validate MITRE ATT&CK mapping

---

## 6. Red Team / Purple Team Exercises 🎯

**Scenario:** Quarterly purple team exercise simulating APT attack chain

**With Event-Horizon (NEW!):**
```bash
1. AI Auto-Discovery: "APT28 style attack - initial access via phishing"
2. IOC Injection: Known C2 IP from threat intel
3. Timezone: Match your SOC's local time
4. Generate 10,000 logs across 6 sourcetypes
5. Blue team detects and responds in real-time
```

**WOW Factor:**
- 🔥 **75+ supported sourcetypes** - complete attack chain coverage
- 🧠 **AI generates realistic TTPs** based on your scenario
- ⏰ **Timezone-aware** - logs appear in SOC's local time
- 🎯 **IOC injection** - test threat intel integration

---

## 7. SIEM Migration & Platform Testing 🔄

**Scenario:** Migrating from legacy SIEM to Splunk, need to validate all use cases

**With Event-Horizon:**
```bash
1. Generate historical baseline (30 days of "normal" traffic)
2. Generate attack scenarios (ransomware, DDoS, data exfil)
3. Validate:
   ✓ All sourcetypes parse correctly
   ✓ Correlation rules trigger
   ✓ Dashboards populate
   ✓ Alerts fire as expected
```

**Results:**
- ✅ Complete SIEM validation in **1 day** (vs weeks of waiting)
- ✅ Zero production data exposure
- ✅ Confidence before go-live

---

## 8. Compliance & Audit Preparation 📋

**Scenario:** Auditor asks "Show me you can detect privilege escalation events"

**With Event-Horizon:**
```bash
1. Generate historical privilege escalation logs
2. Run your detection searches
3. Generate screenshots of alerts
4. Document your detection coverage
```

**No need to:**
- ❌ Wait for real incidents
- ❌ Expose real production logs to auditors
- ❌ Risk missing the detection window

---

## 9. Incident Response Drill 🚨

**Scenario:** Quarterly IR drill - simulate real attack and response

**With Event-Horizon:**
```bash
1. Generate multi-stage attack logs (no one knows when)
2. IR team detects and responds
3. Review response time and actions
4. Identify gaps in playbooks
```

**Example Drill:**
- **T+0**: Phishing email arrives (cisco:esa logs)
- **T+30min**: User clicks link (proxy logs)
- **T+1hr**: Payload executes (Sysmon logs)
- **T+2hr**: Lateral movement begins (WinEventLog)
- **T+3hr**: Data exfiltration (firewall logs)

**Measures:**
- ⏱️ Time to detection
- 🎯 Accuracy of triage
- 🛠️ Effectiveness of response
- 📝 Documentation quality

---

## 10. Zero-Day Simulation (NEW! 🔥)

**Scenario:** Simulate a brand-new attack that your team has never seen

**With Event-Horizon:**
```bash
1. AI Mode: "Simulate zero-day exploit targeting Azure AD"
2. AI generates novel attack pattern
3. Test if existing detections catch it
4. Identify blind spots
5. Create new detection rules
```

**Why This Is Powerful:**
- 🆕 **Test unknown threats** - don't wait for real zero-days
- 🧪 **Validate detection coverage** - find gaps before attackers do
- 📚 **Train analysts** on emerging threats

---

## 11. Vendor POC & Demo Prep 🎬

**Scenario:** Need to demo your SIEM/SOAR capabilities to stakeholders tomorrow

**With Event-Horizon:**
```bash
1. Generate 500k logs showing "business as usual"
2. Generate specific attack (ransomware, insider threat, etc.)
3. Schedule logs with realistic timestamps
4. Push to demo environment
5. Present live detection + response
```

**Benefits:**
- 💼 **Professional presentation** - no "waiting for data" awkwardness
- 🎯 **Control the narrative** - show exactly what you want
- ⚡ **Last-minute prep** - generate demo data in minutes

---

## More Use Cases

Have a use case we didn't cover? [Share it with the community!](https://github.com/PrototypePrime/Event_Horizon/discussions)

**Potential additions:**
- A/B testing detection logic changes
- Training machine learning models
- Generating synthetic data for demos
- Testing data retention policies
- Validating field extractions
- Threat hunting hypothesis testing
- MITRE ATT&CK coverage mapping

---

**[⬅ Back to README](../README.md)** | **[View All Sourcetypes →](SOURCETYPE_REFERENCE.md)**

---

<!-- SEO Keywords -->
<!--
use cases log generator, detection rule testing use cases, soc training scenarios, splunk dashboard testing,
log correlation use cases, attack simulation examples, incident response training, compliance testing scenarios,
detection engineering workflows, threat hunting use cases, splunk performance testing, dashboard population,
analyst training scenarios, soar testing, third-party integration testing, stress testing splunk,
mitre attack simulation, ransomware log simulation, phishing detection testing, lateral movement logs,
purple team exercises, red team drills, zero day simulation, siem migration testing, vendor poc demo
-->
