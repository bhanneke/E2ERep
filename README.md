# E2ERep

**End-to-end automated academic replication pipeline.**

E2ERep takes a paper (DOI or PDF) and runs five deterministic stages: paper analysis, data acquisition, environment setup, analysis execution, and results comparison. Output is a structured replication package — re-analysis code, methodology comparison, and a result JSON — showing whether the original findings hold. Built to support [redo.rocks](https://redo.rocks) reproducibility audits; runs entirely on your own infrastructure (BYOK).

## Quick start

```bash
git clone https://github.com/bhanneke/E2ERep.git
cd E2ERep
# Create .env with your API keys (see BYOK guide below)
pip install -r requirements.txt
python run.py --doi 10.xxxx/xxxxx
```

Output lands in `outputs/` by default. See [BYOK setup](https://redo.rocks/docs/oss) for key configuration.

## API keys required

| Variable | Source | Required |
|---|---|---|
| `ANTHROPIC_API_KEY` | [console.anthropic.com](https://console.anthropic.com) | Yes (or OpenAI) |
| `OPENAI_API_KEY` | [platform.openai.com/api-keys](https://platform.openai.com/api-keys) | Yes (or Anthropic) |
| `SEMANTIC_SCHOLAR_API_KEY` | [api.semanticscholar.org](https://api.semanticscholar.org/api-docs/) | Yes |
| `CROSSREF_EMAIL` | Any valid email | Recommended |

Full setup guide: [redo.rocks/docs/oss](https://redo.rocks/docs/oss)

## Pipeline stages

| Stage | Name | What it does |
|---|---|---|
| 1 | Paper Analysis | Extracts claims, statistical tests, data sources from PDF/DOI |
| 2 | Data Acquisition | Downloads and checksums public datasets |
| 3 | Environment Setup | Installs exact package versions in isolated container |
| 4 | Analysis Execution | Re-runs original analysis code |
| 5 | Results Comparison | Compares outputs against published figures and statistics |

Each stage writes structured JSON consumed by the next.

## Requirements

- Python 3.10+
- At least one LLM API key (Anthropic or OpenAI)
- Semantic Scholar API key (free tier available)

## Contributing

Bug reports, methodology improvements, and dataset coverage contributions welcome via [GitHub Issues](https://github.com/bhanneke/E2ERep/issues) and pull requests.

## Citation

If E2ERep contributes to published work, please cite it:

```
@software{e2erep2024,
  title  = {E2ERep: End-to-End Academic Replication Pipeline},
  author = {redo.rocks},
  year   = {2024},
  url    = {https://github.com/bhanneke/E2ERep}
}
```

## License

Apache 2.0 — see [LICENSE](LICENSE).
Replication packages you produce are your original work, licensed as you choose (CC-BY-4.0 recommended).

---

Hosted replication service and paid audits: [redo.rocks](https://redo.rocks)
