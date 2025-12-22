# Changelog

All notable changes to Event-Horizon will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.1.0] - 2025-12-06

### 🐳 Docker & Infrastructure
- **Containerization Support**: Added Dockerfiles for Backend (Python Slim) and Frontend (Nginx Alpine).
- **Orchestration**: `docker-compose.yml` for one-click deployment.
- **Environment Config**: Full support for `.env` files to configure `SPLUNK_HEC_TOKEN` and other secrets.
- **Nginx Proxy**: Efficient routing for API and Static files behind a single port (8080).
- **Cleanup**: Added `.dockerignore` and refined `.gitignore` for cleaner builds.

### ✨ Template Enhancements (Deep Dive)
- **Windows Security**:
  - Added **Account Lockout (4740)** and **Group Member Added (4728)** events.
  - Fixed XML Timestamp format to ensure perfect extraction in Splunk.
- **Cisco IOS**:
  - Added **Login Success/Failure** events for brute-force simulation.
  - Added **Hardware Failure** (Fan/Power) events for infrastructure monitoring.
  - Refined syslog timestamp format.
- **Palo Alto**:
  - Fixed `pan:traffic` and `pan:threat` empty log generation issue.
  - Corrected CSV-in-Syslog formatting inheritance.

### 🐛 Bug Fixes
- Fixed timestamp injection for XML logs (Splunk now respects event time over ingest time).
- Fixed HEC token header formatting in backend push logic.

---

## [2.0.0] - 2025-12-02

### 🌟 Initial Public Release

**Event-Horizon** - Production-Quality Security Log Generator for SIEM Testing

### Added

#### Core Features
- **87 Production-Accurate Templates** covering major security platforms
  - Firewalls: Palo Alto, Cisco ASA, Fortinet, Checkpoint, pfSense
  - Cloud: AWS CloudTrail, Azure AD, GCP Audit, Office 365
  - Endpoints: Windows EventLog, Sysmon, CrowdStrike, Carbon Black
  - Web: Apache, IIS, NGINX, Squid
  - Email: Proofpoint, Mimecast, Cisco ESA
  - Network: Juniper, Cisco IOS, Aruba

#### AI-Powered Features
- **Ollama Integration** for local AI log generation
- **Attack Scenario Auto-Discovery** - describe attack, AI selects sourcetypes
- **AI Fallback** for unsupported sourcetypes
- **Support for multiple models**: gpt-oss:120b-cloud, llama3, deepseek

#### Generation Modes
- **Single Mode**: High-volume generation of one sourcetype
- **Multi-Mode (Manual)**: Select specific sourcetypes for correlation
- **Multi-Mode (AI)**: AI-orchestrated attack chains

#### Advanced Features
- **IOC Injection**: Embed specific IPs, domains, hashes in logs
- **Time Travel**: Generate logs for any historical date range
- **Format Validation**: Automatic log format verification
- **Splunk HEC Integration**: Direct push to Splunk (raw & event endpoints)
- **Golden Master System**: First AI-generated log becomes template

#### UI/UX
- **Modern React Interface** with dark mode
- **Real-time Ollama Connection Status**
- **Syntax-Highlighted Log Preview** (IPs, timestamps, status codes)
- **Progressive Disclosure**: Mode-based UI complexity
- **Download Options**: JSON, text, copy to clipboard

#### Backend
- **FastAPI REST API** with async support
- **Template-First Architecture** (1000+ logs/sec)
- **AI Fallback** (45 logs/sec)
- **Smart HEC Routing** (raw vs event endpoint)
- **Comprehensive Logging** system
- **CORS Support** for frontend integration

#### Documentation
- Comprehensive README with use cases
- Architecture deep dive
- Installation guide (Windows/Mac/Linux)
- Quick start tutorial
- Contributing guide with template creation examples
- FAQ with 20+ questions
- Roadmap with future features
- Backend API documentation
- Frontend component documentation

#### Developer Experience
- **Smoke Test Suite** - validates all 80+ templates
- **Format Validation Tests**
- **Variety Testing** for log diversity
- **Gap Analysis Tests** for data consistency
- **Example Scripts** for bulk generation

### Technical Details

- **Languages**: Python 3.8+, JavaScript/React 19
- **Frameworks**: FastAPI, React, Vite
- **Styling**: TailwindCSS with custom dark theme
- **AI**: Ollama local LLM integration
- **Privacy**: 100% local, no external APIs required
- **Deployment**: Air-gapped capable

### License

Non-Commercial License - Free for personal, educational, and research use

---

## [Unreleased]

### Planned for v2.1 (Q1 2026)
- 20+ new templates (EDR, cloud services)
- Performance mode (10,000+ logs/sec)
- Batch export improvements
- Enhanced UI features

### Planned for v3.0 (Q3 2026)
- DeepSeek validation loop
- Real-time log streaming
- Kubernetes deployment support
- Multi-SIEM format support

See [ROADMAP.md](docs/ROADMAP.md) for future plans.

---

## Version History

- **2.0.0** (2025-12-02) - Initial public release as Event-Horizon
- **1.x** - Internal development versions (Splunk-Log-Forge)

---

**[View all releases →](https://github.com/PrototypePrime/Event-Horizon/releases)**

<!-- 
Template for future releases:

## [X.Y.Z] - YYYY-MM-DD

### Added
- New features

### Changed
- Changes in existing functionality

### Deprecated
- Soon-to-be removed features

### Removed
- Removed features

### Fixed
- Bug fixes

### Security
- Vulnerability fixes
-->
