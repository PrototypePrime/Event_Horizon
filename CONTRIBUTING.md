# Contributing to Event-Horizon

Thank you for your interest in contributing to Event-Horizon! 🎉

## 📋 Ways to Contribute

### 🐛 Report Bugs
- Use the [Bug Report template](https://github.com/PrototypePrime/Event-Horizon/issues/new?template=bug_report.md)
- Include clear reproduction steps
- Provide environment details (OS, Docker version, etc.)

### ✨ Suggest Features
- Share ideas in [Discussions](https://github.com/PrototypePrime/Event-Horizon/discussions/categories/ideas)
- Vote on existing feature requests
- Explain the use case and problem you're solving

### 📝 Request New Templates
- Use the [Template Request form](https://github.com/PrototypePrime/Event-Horizon/issues/new?template=template_request.md)
- Include sample logs if possible (sanitized)
- Link to vendor documentation

### 📖 Improve Documentation
- Fix typos or unclear explanations
- Add examples and use cases
- Translate documentation

## 🚀 Development Setup

```bash
# Clone the repository
git clone https://github.com/PrototypePrime/Event-Horizon.git
cd Event-Horizon

# Using Docker (recommended)
docker compose up -d

# Or from source
cd backend && pip install -r requirements.txt && python main.py
cd frontend && npm install && npm run dev
```

## 📐 Code Style Guidelines

### Python (Backend)
- Follow PEP 8 style guide
- Use type hints where practical
- Document functions with docstrings

### JavaScript/React (Frontend)
- Use ESLint configuration provided
- Prefer functional components with hooks
- Keep components focused and reusable

## 🔄 Pull Request Process

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### PR Requirements
- [ ] Code follows project style guidelines
- [ ] Self-reviewed the code
- [ ] Added/updated documentation if needed
- [ ] Tested changes locally

## 🎭 Adding New Log Templates

See the [Backend README](backend/README.md#adding-new-templates) for detailed instructions on creating new sourcetype templates.

### Quick Template Checklist
- [ ] Template follows vendor's actual log format
- [ ] Includes realistic field values
- [ ] Supports dynamic IOC injection
- [ ] Tested with Splunk parsing

## 💬 Questions?

- Check the [FAQ](docs/FAQ.md)
- Ask in [Q&A Discussions](https://github.com/PrototypePrime/Event-Horizon/discussions/categories/q-a)

## 📜 License

By contributing, you agree that your contributions will be licensed under the same [Non-Commercial License](LICENSE) as the project.

---

**Thank you for making Event-Horizon better!** ⭐
