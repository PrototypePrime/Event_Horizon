# ⚡ Quick Start Guide

<div align="center">

### **Get Event-Horizon running in under 2 minutes**
*One command to rule them all*

</div>

---

## 🐳 Docker (Recommended)

### Prerequisites
- **Docker** installed ([Get Docker](https://docs.docker.com/get-docker/))
- **Ollama** (optional, for AI features) - [ollama.com](https://ollama.com)

### One-Command Launch
```bash
docker run -d -p 3000:3000 --name event-horizon ghcr.io/prototypeprime/event-horizon:latest
```

**Open:** [http://localhost:3000](http://localhost:3000)

### With Ollama (AI Features)
```bash
docker run -d -p 3000:3000 \
  -e OLLAMA_BASE_URL=http://host.docker.internal:11434 \
  --name event-horizon \
  ghcr.io/prototypeprime/event-horizon:latest
```

---

## 🎮 How to Use

### 1️⃣ Single Mode
Generate high volumes of a specific log type.

1. Select **Single Mode**
2. Choose a **Sourcetype** (e.g., `pan:traffic`)
3. Set **Count** (e.g., 10,000)
4. Click **Generate Logs**

### 2️⃣ Multi-Mode (Manual)
Correlate events across specific sources.

1. Select **Multi Mode**
2. **Uncheck** "AI Auto-Discover"
3. Add multiple sourcetypes
4. Click **Generate Logs**

### 3️⃣ AI Auto-Discovery
Let AI select sourcetypes for realistic attack scenarios.

1. Select **Multi Mode**
2. **Check** "AI Auto-Discover"
3. Enter an **Attack Scenario** (e.g., "Ransomware attack")
4. Click **Generate Logs**

---

## 🔗 Push to Splunk

1. Click **Settings** (⚙️)
2. Enter your **HEC URL** and **Token**
3. Click **Test Connection**
4. Generate logs and click **Push to Splunk**

---

## 🛠️ Troubleshooting

| Issue | Solution |
|-------|----------|
| Port conflict | Use `-p 3001:3000` to change port |
| Ollama not connecting | Verify `OLLAMA_BASE_URL` is correct |
| Container won't start | Run `docker logs event-horizon` |

---

## 💡 Feature Requests & Feedback

Have ideas to improve Event-Horizon?

- 💬 [Join Discussions](https://github.com/PrototypePrime/Event_Horizon/discussions)
- 💡 [Request a Feature](https://github.com/PrototypePrime/Event_Horizon/discussions/new?category=ideas)
- 🐛 [Report a Bug](https://github.com/PrototypePrime/Event_Horizon/issues)

---

**[⬅ Back to README](../README.md)** | **[Full Installation Guide →](INSTALLATION.md)**
