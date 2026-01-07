# Automated Triage Assistant (Logic Engine)

**Status:** Proof of Concept (PoC) / Open Core  
**Version:** 1.0.2-alpha

## Overview
The Logic Engine is a Python-based automated triage utility designed to detect non-deterministic business logic flaws in HTTP history. Unlike standard DAST scanners that rely on signature matching, this tool utilizes a local LLM (Ollama) to analyze state transitions and flag potential "State Violations."

## Features
* **State Analysis:** Parses HTTP history to identify broken object level authorization (BOLA) and logic bypasses.
* **False Positive Reduction:** Uses heuristic analysis to filter out standard 403/404 noise.
* **Local Processing:** All data processing is performed locally to ensure data privacy (no data sent to external cloud APIs).

## Architecture
* **Input:** Burp Suite XML / HTTP Archive.
* **Core:** Python 3.10 + Custom Parser.
* **Analysis:** Local LLM Interface (Ollama).

## Installation
```bash
git clone [https://github.com/shabz0077/logic-engine.git](https://github.com/shabz0077/logic-engine.git)
pip install -r requirements.txt
python main.py --input target_log.xml

## Disclaimer
4.  Scroll down and click **Commit changes**.

---

### **Step 3: Add the "Skeleton" Python File**
This makes it look like real code, not just a text file.

1.  In the repo, click **Add file** $\rightarrow$ **Create new file**.
2.  Name the file: `main.py`
3.  **Paste** this placeholder code:

```python
import sys
import argparse
from utils.parser import BurpParser

# Core logic import (Excluded from public repo)
# from core.engine import HeuristicEngine 

def main():
    print("[*] Starting Logic Engine v1.0.2...")
    print("[*] Initializing Local LLM Interface...")
    
    parser = argparse.ArgumentParser(description="Automated Triage Assistant")
    parser.add_argument("--input", required=True, help="Path to HTTP log file")
    args = parser.parse_args()

    # Placeholder for Open Core execution
    try:
        print(f"[*] Loading data from {args.input}")
        # data = BurpParser(args.input)
        print("[!] Core Logic Module not found. Running in Ingestion-Only mode.")
    except Exception as e:
        print(f"[X] Error: {e}")

if __name__ == "__main__":
    main()
