# Contributing to AquaPurify-RL

Thank you for your interest in contributing to AquaPurify-RL! 🌊

This project aims to advance AI-driven water purification for global clean water access. Every contribution — whether code, documentation, bug reports, or ideas — directly supports this mission.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Making Changes](#making-changes)
- [Testing](#testing)
- [Code Style](#code-style)
- [Pull Request Process](#pull-request-process)
- [Priority Areas](#priority-areas)

---

## 🤝 Code of Conduct

This project adheres to the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/). Be respectful, inclusive, and constructive.

---

## 🚀 Getting Started

1. **Fork** the repository
2. **Clone** your fork: `git clone https://github.com/YOUR_USERNAME/aquapurify-rl.git`
3. **Add upstream**: `git remote add upstream https://github.com/yourusername/aquapurify-rl.git`
4. **Create a branch**: `git checkout -b feature/your-feature-name`

---

## 🛠️ Development Setup

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dev dependencies
pip install -r requirements.txt
pip install ruff black isort mypy pytest pytest-cov

# Install pre-commit hooks
pip install pre-commit
pre-commit install

# Verify setup
python -c "from src.reinforcement_learning.environment import WaterPurificationEnv; print('✅ Setup OK')"
```

---

## ✏️ Making Changes

### Branch Naming
- `feature/description` — new features
- `fix/description`     — bug fixes
- `docs/description`    — documentation
- `perf/description`    — performance improvements
- `refactor/description`— code refactoring

### Commit Messages (Conventional Commits)
```
feat: add TD3 algorithm support
fix: correct pH normalisation in environment
docs: update RL training tutorial
perf: optimise SHAP computation by 3x
test: add anomaly detection edge case tests
```

---

## 🧪 Testing

All PRs must include tests. Run the full test suite:

```bash
# All tests
pytest tests/ -v --cov=src --cov-report=html

# Specific module
pytest tests/unit/test_all.py::TestWaterPurificationEnv -v

# Fast check (skip slow tests)
pytest tests/unit/ -v -m "not slow"

# Coverage report
open htmlcov/index.html
```

**Coverage Requirements:**
- New features: ≥ 80% coverage
- Bug fixes: existing coverage maintained
- Core RL environment: ≥ 90% coverage

---

## 🎨 Code Style

We use **ruff** + **black** + **isort**:

```bash
# Auto-format
black src/ tests/
isort src/ tests/

# Lint (check only)
ruff check src/ tests/

# Type check
mypy src/ --ignore-missing-imports
```

**Style Guidelines:**
- Type hints on all public functions
- Docstrings for all classes and public methods (NumPy style)
- Maximum line length: 100 characters
- No magic numbers — use named constants
- Meaningful variable names (no `x`, `tmp`, etc. outside math)

---

## 🔄 Pull Request Process

1. **Update** your branch from upstream: `git pull upstream main`
2. **Run** all tests: `pytest tests/ -v`
3. **Run** linting: `ruff check src/` and `black --check src/`
4. **Update** documentation if needed
5. **Open PR** with the provided template
6. **Respond** to review comments promptly

PRs are reviewed within **48 hours** for small changes, **5 business days** for large features.

---

## 🎯 Priority Areas

We especially welcome contributions in:

| Area | Priority | Difficulty |
|------|----------|-----------|
| Computer Vision turbidity analysis | High | Medium |
| Hardware-in-the-loop ESP32 tests | High | Medium |
| Offline RL (D4RL) integration | Medium | High |
| Federated Learning across plants | Medium | High |
| Additional contamination scenarios | High | Low |
| Dashboard improvements | Medium | Low |
| Documentation translations | High | Low |
| Raspberry Pi deployment guide | High | Low |

---

## 📧 Questions?

Open a [GitHub Discussion](https://github.com/yourusername/aquapurify-rl/discussions) or reach out via the issue tracker.

**Together, we can make clean water accessible to everyone. 💧**
