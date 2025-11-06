# 🧬 cryptoquantai-core
### Core Infrastructure & Shared Utilities for the CryptoQuantAI Ecosystem

`cryptoquantai-core` is the foundational library for the **CryptoQuantAI** ecosystem.  
It provides shared utilities, configuration systems, abstract base classes, logging tools,  
and common infrastructure used across all CryptoQuantAI repositories:

- cq-ohlcv – OHLCV data downloader  
- cq-indicators – Technical indicators  
- cq-backtester – Backtesting engine  
- cq-trader – Live trading engine  
- cq-tradingview – Chart rendering  
- cq-aimodels – ML/DL models  
- cq-aiagent – ChatGPT-driven trading agents  

This package ensures architectural consistency, performance reliability, and development simplicity.

---

## 🚀 Features

- ✅ Unified Logging (console + rotating file handlers)  
- ✅ Configuration loader (YAML / JSON / TOML)  
- ✅ Environment variable manager (.env support)  
- ✅ Base classes for loaders, indicators, strategies, agents, and ML models  
- ✅ Time utilities (timestamp helpers, TZ-safe conversion)  
- ✅ Filesystem helpers (cache dirs, data dirs, auto-create paths)  
- ✅ Custom exception framework  
- ✅ Lightweight Event Bus for internal signaling  

Designed to be lightweight, dependency-free, and production-ready.

---

## 📦 Installation

```bash
pip install cryptoquantai-core
```

Or install as part of the entire ecosystem:

```bash
pip install cq-ohlcv cq-indicators cq-backtester cq-trader
```

---

## 💡 Quick Start

### ✅ Load Config

```python
from cryptoquantai_core.config import load_config

config = load_config("config.yaml")
print(config)
```

---

### ✅ Create Logger

```python
from cryptoquantai_core.logger import get_logger

log = get_logger("demo")
log.info("Logger initialized!")
```

---

### ✅ Work with Paths

```python
from cryptoquantai_core.paths import get_data_dir, ensure_dir

data_folder = get_data_dir("ohlcv")
ensure_dir(data_folder)

print("Data path:", data_folder)
```

---

### ✅ Base Class Example

```python
from cryptoquantai_core.base import BaseDataLoader

class MyLoader(BaseDataLoader):
    def load(self):
        return {"status": "loaded"}
```

---

## 🗂 Folder Structure

```
cryptoquantai-core/
│
├── cryptoquantai_core/
│   ├── __init__.py
│   │
│   ├── base/
│   │   ├── base_data_loader.py
│   │   ├── base_indicator.py
│   │   ├── base_strategy.py
│   │   ├── base_model.py
│   │   ├── base_agent.py
│   │
│   ├── config/
│   │   ├── loader.py
│   │
│   ├── logger/
│   │   ├── logger.py
│   │
│   ├── utils/
│   │   ├── time.py
│   │   ├── paths.py
│   │   ├── exceptions.py
│   │   ├── env.py
│   │
│   └── events/
│       ├── event_bus.py
│
├── tests/
├── examples/
└── README.md
```

---

## 📅 Roadmap

- ✅ Standardized interfaces for all CryptoQuantAI modules  
- ✅ Improved config merging system  
- ⏳ Typed runtime validation for configs  
- ⏳ Async event bus  
- ⏳ Rust-accelerated utils via pyo3  

---

## 🤝 Contributing

We welcome contributions from developers, researchers, and traders.

**Guidelines:**

- Follow PEP8 + type hints  
- Format using **Black**  
- Add docstrings  
- Use meaningful commit messages  

---

## ⚖️ License

MIT License — free for personal and commercial use.

---

## 👨‍💻 Maintained By

**CryptoQuantAI Development Team**  
AI-Powered Trading Infrastructure
