# ❓ Frequently Asked Questions

## Installation & Setup

### Q: What are the minimum system requirements?
**A:** 
- **Docker:** Docker Engine 20.10+ or Docker Desktop
- **RAM:** 4GB minimum (8GB recommended for AI features)
- **Disk:** 2GB for Docker image
- **Port:** 3000 (default, configurable)



---

### Q: Can I run this on Windows/Mac/Linux?
**A:** Yes! Event-Horizon is cross-platform:
- ✅ Windows 10/11
- ✅ macOS 11+
- ✅ Ubuntu 20.04+, Debian, CentOS, RHEL

---

### Q: Do I need Ollama for basic usage?
**A:** **No** - Ollama is only required for AI-powered features:
- AI attack scenario generation
- AI Auto-Discovery mode
- Custom content generation

For template-based generation (81 sourcetypes), no AI is needed. You can generate millions of logs using templates alone.

---

### Q: How do I connect Docker to Ollama?
**A:** Set the `OLLAMA_BASE_URL` environment variable when running the container:

```bash
# If Ollama is on your host machine:
docker run -p 3000:3000 \
  -e OLLAMA_BASE_URL=http://host.docker.internal:11434 \
  ghcr.io/prototypeprime/event-horizon:latest

# If Ollama is on a different server:
docker run -p 3000:3000 \
  -e OLLAMA_BASE_URL=http://192.168.1.100:11434 \
  ghcr.io/prototypeprime/event-horizon:latest
```

---

### Q: Which Ollama model should I use?
**A:** **Recommended:** `gpt-oss:20b-cloud` (default)

This smaller model is chosen for:
- **Speed** - Generates logs quickly without timeouts
- **Good quality** - Produces realistic, well-formatted logs
- **Efficient** - Works well with the two-phase hybrid approach

```bash
# Pull the recommended model:
ollama pull gpt-oss:20b-cloud

# For higher quality (slower):
ollama pull gpt-oss:120b-cloud
```

**Alternative models:**
- `gpt-oss:120b-cloud` - Better quality, slower
- `qwen3-coder:480b-cloud` - Best for complex scenarios
- `deepseek-v3.1:671b-cloud` - Highest quality, slowest

**How it works:** Event-Horizon uses a two-phase approach:
1. AI generates ONE example log as a template
2. AI generates field variations for faster bulk generation
3. If AI fails, a smart fallback generates realistic logs



### Q: Can I use this offline/air-gapped?
**A:** **Yes!** Templates work 100% offline with no external API calls. For AI features in air-gapped environments, point `OLLAMA_BASE_URL` to a local Ollama instance on your network.



---

## Usage & Features

### Q: What's the difference between Single and Multi mode?
**A:**

| Mode | When to Use | Example |
|------|-------------|---------|
| **Single** | Generate high volume of one sourcetype | "I need 100k `pan:traffic` logs for dashboard testing" |
| **Multi (Manual)** | Specific multi-source scenarios | "Test correlation across `cisco:asa` + `WinEventLog:Security`" |
| **Multi (AI)** | Unknown/complex attack scenarios | "Simulate ransomware attack" (AI selects sources) |

---

### Q: How accurate are the generated logs?
**A:** **Templates: 100% accurate** to vendor documentation. We validate against:
- Official vendor format specs
- Real production logs (sanitized)
- Splunk Add-on parsers
- Community feedback

**AI Content: Realistic but not perfect.** AI generates realistic values (IPs, usernames, actions) but may occasionally produce edge cases. Always validate in your environment.

---

### Q: Can I customize the templates?
**A:** The Docker image comes with 81 pre-built templates covering all major security platforms. For custom sourcetype requests, please [open a feature request](https://github.com/PrototypePrime/Event_Horizon/discussions).

---

### Q: Can I add new sourcetypes?
**A:** **Yes!** Submit a feature request via [GitHub Discussions](https://github.com/PrototypePrime/Event_Horizon/discussions) with:
- Must match real vendor format
- Include vendor documentation link
- Provide example logs
- Test with Splunk Add-on (if available)

[See the Sourcetype Reference for template details →](SOURCETYPE_REFERENCE.md)

---

### Q: What's the maximum number of logs I can generate?
**A:** **No hard limit**, but practical considerations:
- **Memory:** ~200MB per 100k logs (in browser)
- **Browser:** Chrome/Firefox can handle ~500k logs before slowdown
- **Splunk HEC:** Limited by your network/Splunk capacity

**Recommendation:** Generate in batches of 100k for best performance.

---

## Technical Questions

### Q: How does the Template + AI hybrid work?
**A:**
```
User Request: "Generate pan:traffic logs for ransomware attack"
           ↓
    ┌──────┴──────┐
    │  Template   │ ← Provides perfect PAN CSV structure
    │   Engine    │   (headers, field order, delimiters)
    └──────┬──────┘
           │
           ↓
    ┌──────┴──────┐
    │ AI Engine   │ ← Generates realistic content
    │  (Ollama)   │   (malicious IPs, attack patterns)
    └──────┬──────┘
           │
           ↓
    Perfect logs with realistic attack content
```

---

### Q: Which Ollama models are supported?
**A:**


---

### Q: How do you handle timestamps?
**A:** Smart time distribution:
- **Relative Mode:** "Last 7 days" - evenly distributes logs
- **Absolute Mode:** "Jan 1-7, 2024" - specific date range
- **Attack Mode:** Realistic progression (e.g., recon → exploit → exfil)

All timestamps respect the sourcetype's native format.

---

## Troubleshooting

### Q: "Connection refused" error for Ollama
**A:** Check your `OLLAMA_BASE_URL` environment variable:

```bash
# Verify Ollama is accessible from Docker
# If Ollama is on your host:
docker run --rm curlimages/curl http://host.docker.internal:11434

# If you get a response, use:
-e OLLAMA_BASE_URL=http://host.docker.internal:11434
```



---

### Q: Logs generated but not parsing in Splunk
**A:** Most likely:
1. **Wrong sourcetype:** Verify sourcetype name matches exactly
2. **Add-on needed:** Some sourcetypes require vendor Splunk Add-ons
3. **Time parsing:** Check if Splunk is extracting timestamps correctly

See [SOURCETYPE_REFERENCE.md](SOURCETYPE_REFERENCE.md) for required add-ons per sourcetype.



---

### Q: Application won't start
**A:** Check Docker logs:
```bash
docker logs <container_id>

# Or with docker compose:
docker compose logs
```

Common issues:
- **Port conflict:** Port 3000 already in use (use `-p 3001:3000` to change)
- **Permission denied:** Ensure Docker Desktop is running



---

### Q: AI generation is very slow
**A:** Event-Horizon uses a hybrid approach to minimize this:
- **Two-phase generation:** AI creates one template, then variations (much faster)
- **Fallback:** If AI times out, realistic logs are still generated
- **Smaller model:** Default `gpt-oss:20b-cloud` is optimized for speed

**Tips:**
- Ensure Ollama is running on GPU if available
- Use template-based generation (81 sourcetypes) for instant results

---

## Compliance & Legal

### Q: Can I use this in production?
**A:** **We strongly recommend using Event-Horizon in non-production environments.** 

This tool is designed for **development, testing, and training**. While it is safe to run, the high volume of synthetic data can:
- Skew production analytics and baselines
- Impact license usage quotas
- Confuse real incident response teams

**Best Practice:** Always target a dedicated test index (e.g., `index=test`) or use a separate development instance.

**Ideal Environments:**
- ✅ Detection Engineering Lab
- ✅ SOC Training Range
- ✅ Staging/QA Environment
- ✅ Local Development

---

### Q: What's the license?
**A:** **Non-Commercial License:**
- ✅ Free for personal use
- ✅ Free for educational use
- ✅ Free for research
- ❌ Commercial use requires permission

See [LICENSE](../LICENSE). for full terms.

---

### Q: Does this create "real" security events?
**A:** **No.** All logs are **synthetic** and contain:
- ❌ No real PII (personally identifiable information)
- ❌ No production data
- ❌ No actual security events

Logs are realistic but fictional, designed for testing only.

---

## Community & Support

### Q: How do I report a bug?
**A:** [Open an issue on GitHub](https://github.com/PrototypePrime/Event_Horizon/issues) with:
- Error message
- Steps to reproduce
- Your environment (OS, Python version, etc.)

---

### Q: Can I request a new sourcetype?
**A:** **Yes!** Two options:
1. [Open a feature request](https://github.com/PrototypePrime/Event_Horizon/discussions)
2. Submit a feature request via [GitHub Discussions](https://github.com/PrototypePrime/Event_Horizon/discussions)

---

### Q: How do I stay updated?
**A:**
- ⭐ Star the [GitHub repo](https://github.com/PrototypePrime/Event_Horizon)
- 💬 Join [GitHub Discussions](https://github.com/PrototypePrime/Event_Horizon/discussions)
- 📧 Subscribe to [release notifications](https://github.com/PrototypePrime/Event_Horizon/releases)

---

## Have More Questions?

- 💬 **Community:** [GitHub Discussions](https://github.com/PrototypePrime/Event_Horizon/discussions)
- 🐛 **Bug Reports:** [Issue Tracker](https://github.com/PrototypePrime/Event_Horizon/issues)
- 📧 **Direct Support:** [mathan1702@gmail.com](mailto:mathan1702@gmail.com)

---

**[⬅ Back to README](../README.md)**

---

<!-- SEO Keywords -->
<!--
splunk log generator faq, log generation questions, splunk testing faq, detection engineering questions,
log generator help, splunk hec questions, ollama faq, ai log generation questions,
splunk troubleshooting, log format questions, template questions, soc training faq,
log correlation faq, attack simulation questions, splunk performance questions,
air-gapped splunk faq, compliance logging questions, synthetic data questions
-->
