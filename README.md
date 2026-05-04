# Azoth

Portable agentic toolkit: skills, agents, pipelines, and governance patterns.

## Install (consumer project)

From a clone of this repository:

```bash
pip install -r requirements-dev.txt   # or your venv equivalent
bash install.sh                         # or install.ps1 on Windows — project mode
```

Then open **`CLAUDE.md`** in your AI tool and follow the bootloader (**ACTIVATE → SURVEY → OPERATE → HARDEN**).

## What this repo is

**Azoth** is the public, installable Azoth toolkit (see architecture docs in `docs/`). It is extracted from the private **root-azoth** workshop using `scripts/azoth_extract_product.py` and `sync-config.yaml` (`product_extraction`).

## License

Licensed under the [PolyForm Noncommercial License 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0/). The copyright holder retains all rights not expressly granted. **Commercial use** (outside the license’s permitted noncommercial purposes) requires a **separate written agreement** — contact via [github.com/yiwei79](https://github.com/yiwei79).

## Contributing / upstream

Development happens in the **root-azoth** scaffold; changes here flow from mechanical extraction — do not treat this tree as the authoritative workshop copy.

## Fresh GitHub Copilot project

From an empty target repository, force the Copilot surface explicitly:

```bash
AZOTH_PLATFORMS=copilot bash /path/to/azoth/install.sh
```

Windows PowerShell:

```powershell
$env:AZOTH_PLATFORMS = "copilot"
pwsh -File C:\path\to\azoth\install.ps1
```

The Copilot install creates `.github/copilot-instructions.md`, `.github/prompts/`,
`.github/agents/`, `AGENTS.md`, `CLAUDE.md`, `azoth.yaml`, and `.azoth/kernel/`.
If no `AZOTH_PLATFORMS` override is set, the installers include GitHub Copilot
alongside detected tools; if no tools are detected, they default to Claude Code +
GitHub Copilot.
