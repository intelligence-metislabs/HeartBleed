# HeartBleed OSINT Toolkit 🩸

[![PyPI version](https://img.shields.io/pypi/v/heartbleed-osint.svg)](https://pypi.org/project/heartbleed-osint/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)

HeartBleed is a modular, high-performance command-line OSINT toolkit designed to discover and correlate publicly available social media and online accounts belonging to a target individual.

**Developed by: Alpha-07 (Metis Labs)**

---

## 📑 Table of Contents
- [🚀 Features](#-features)
- [🛠️ Architecture](#️-architecture)
- [📦 Installation](#-installation)
- [📖 Usage](#-usage)
- [🌐 Domain Intelligence](#-domain-intelligence)
- [📄 Professional Export](#-professional-export)
- [🕸️ Multi-Target Workspaces](#️-multi-target-workspaces)
- [🛡️ Security & Ethics](#️-security--ethics)
- [🗺️ Roadmap](#️-roadmap)

---

## 🚀 Features

- **Concurrent Collection**: Parallelized platform scanning for maximum speed.
- **Identity Correlation**: Advanced scoring engine to determine profile ownership probability.
- **Platform Support**: GitHub, GitLab, Reddit, Instagram, X (Twitter), and **Gravatar**.
- **Email Discovery**: Find profiles linked to an email address.
- **Domain Intelligence**: Analyze domains for WHOIS, DNS records (MX, SPF), and subdomains.
- **Username Mutation**: Automatically check variations like `user_`, `user123`, `realuser` (`--mutate`).
- **Digital Footprint Dorker**: Instant clickable links for Pastebin, data leaks, and tech forums.
- **Persona Profiler**: Local, rule-based extraction of Job Titles, Tech Stacks, and Interests.
- **Multi-Target Workspaces**: Group related scans and map overlaps between targets.
- **Professional Reporting**: Generate JSON, Interactive HTML (with Graphs), and **PDF reports**.
- **Ethics-First**: Strictly operates on publicly accessible data (no auth bypassing).

## 🛠️ Architecture

HeartBleed follows **Clean Architecture** principles:

- **`heartbleed/core`**: Business logic, data models, and the search orchestrator.
- **`heartbleed/collectors`**: Platform-specific plugins (now with Email support).
- **`heartbleed/modules`**: Specialized intelligence modules (Domain Analysis).
- **`heartbleed/analyzers`**: Correlation, Dorking, and Persona Profiling.
- **`heartbleed/reporters`**: Terminal and Interactive HTML formatters.
- **`heartbleed/exports`**: JSON and PDF export logic.
- **`heartbleed/database`**: SQLite persistence layer.

## 📦 Installation

### Prerequisites
- Python 3.11+
- Pip

### Recommended Setup (Pip)
You can install HeartBleed directly from PyPI:
```bash
pip install heartbleed-osint
```

### Installation from Source
```bash
git clone https://github.com/intelligence-metislabs/HeartBleed.git
cd HeartBleed
pip install .
```

This will install the `heartbleed` command globally.

## 📖 Usage

### Basic Scan
```bash
# Scan by username
heartbleed scan johndoe

# Scan by email
heartbleed scan user@example.com --type email
```

### 🌐 Domain Intelligence
Analyze a domain's footprint, records, and subdomains.
```bash
heartbleed domain scan example.com
```

### 📄 Professional Export
Generate a PDF report for your investigation.
```bash
# Export existing investigation ID 1 to PDF
heartbleed report 1 --format pdf
```

### 🕸️ Multi-Target Workspaces
```bash
# Create a workspace and add targets to it
heartbleed workspace create "Case 001"
heartbleed scan alias_1 --workspace 1 --mutate
heartbleed workspace report 1
```

## 🛡️ Security & Ethics
HeartBleed is an OSINT tool. It must never be used for unauthorized access or stalking. All information collected originates from publicly accessible sources. Users are responsible for complying with local laws and the terms of service of the platforms being scanned.

## 🗺️ Roadmap
- [x] Support for Reddit, X, and Instagram.
- [x] Graph-based visualization of correlations.
- [x] Multi-target workspace mapping.
- [x] Username mutation engine.
- [x] Local bio persona profiling.
- [x] Email-to-Account discovery (v0.3).
- [x] Domain-specific intelligence modules (v0.3).
- [x] Export to PDF report (v0.3).
- [ ] Automated image reverse-search links.
- [ ] Dark web forum search modules.
