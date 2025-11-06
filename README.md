cryptoquantai-core
==================

Core Utilities, Base Classes, and Shared Infrastructure for the CryptoQuantAI Ecosystem

cryptoquantai-core is the foundational library for the CryptoQuantAI organization.
It provides all low-level infrastructure, shared utilities, and abstract interfaces used by:

- cq-ohlcv – Fast OHLCV downloader
- cq-indicators – Indicator library
- cq-backtester – Backtesting engine
- cq-trader – Live trading engine
- cq-tradingview – Chart renderer
- cq-aimodels – AI model training + inference
- cq-aiagent – ChatGPT-driven trading agent

This package ensures consistency, stability, and clean architecture across the entire suite.

------------------------------------------------------------
Features
------------------------------------------------------------

- Config system: YAML/JSON/TOML loader with layered fallback
- Logging utilities: Unified logging across all modules
- Environment loader: Safe .env loading and validation
- Path utilities: Auto-created folders, cache mgmt, directory helpers
- Error handling: Custom exceptions for predictable flow
- Base abstract classes: DataLoaders, Indicators, Strategies, Models, Agents
- Time utilities: Timestamp tools and timezone conversions
- Type-safe settings dataclasses
- Event Bus: Lightweight publish/subscribe messaging

------------------------------------------------------------
Installation
------------------------------------------------------------

pip install cryptoquantai-core

Or install full ecosystem:

pip install cq-ohlcv cq-indicators cq-backtester cq-trader

cryptoquantai-core will install automatically.

------------------------------------------------------------
Quick Start
------------------------------------------------------------

1. Load Config
----------------
from cryptoquantai_core.config import load_config
config = load_config("config.yaml")
print(config)

2. Logger
----------------
from cryptoquantai_core.logger import get_logger
log = get_logger("example")
log.info("Logger initialized!")

3. Paths
----------------
from cryptoquantai_core.paths import ensure_dir, get_data_dir
data_dir = get_data_dir("ohlcv")
ensure_dir(data_dir)
print("Data folder:", data_dir)

4. Base Class Example
----------------
from cryptoquantai_core.base import BaseDataLoader

class MyLoader(BaseDataLoader):
    def load(self):
        return {"message": "example"}

------------------------------------------------------------
Package Structure
------------------------------------------------------------

cryptoquantai-core/
│
├── cryptoquantai_core/
│   ├── __init__.py
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

------------------------------------------------------------
Philosophy
------------------------------------------------------------

CryptoQuantAI ecosystem principles:

- Modular – every package works independently
- Extensible – add indicators, strategies, models easily
- Fast – optimized utilities without heavy dependencies
- Safe – predictable error handling across all repos
- Production-ready – clean architecture for real trading systems

------------------------------------------------------------
Contributing
------------------------------------------------------------

We welcome contributions.
Follow:

- Conventional commits
- Black formatting
- PEP8 coding standards
- Typed function signatures

Submit PRs or open issues anytime.

------------------------------------------------------------
License
------------------------------------------------------------

MIT License — free for personal and commercial use.

------------------------------------------------------------
Maintained By
------------------------------------------------------------

CryptoQuantAI Development Team
AI-Powered Trading Infrastructure
