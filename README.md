# Go Email Extractor Pro

High-performance email extraction tool for large-scale website crawling.  
It discovers contact pages and extracts emails using OCR, JSON-LD parsing, obfuscation decoding, and multilingual contact discovery.

Developed by Dr.Anach — Telegram: [@dr.anach](https://t.me/dr.anach)

---

## Highlights

- Fast concurrent crawling with retry and rate-limit controls
- Smart contact-page discovery using keyword scoring and sitemap signals
- Extraction from HTML text, `mailto:`, JSON-LD, and image OCR
- Quality filters for placeholders, disposable domains, provider templates, and malformed addresses
- Resume support via checkpoint + per-run output directories
- Realtime dashboard with progress and quality telemetry

## Use Cases

- B2B lead generation
- Agency prospecting
- Contact enrichment pipelines
- Competitive website intelligence

## Requirements

- Go Email Extractor Pro binary (`.exe` / Linux / macOS build)
- Domains list file (configured in `config.json`)
- Data files under `data/`
- Optional OCR: [Tesseract](https://github.com/tesseract-ocr/tesseract) installed and available on `PATH`

## Quick Start

1) Prepare config:

- Copy `config.example.json` to `config.json`
- Put your domain list in the file referenced by `domains_file_path`

2) Run:

- **Windows**

```bash
go-email-extractor-pro.exe -config config.json -dashboard 127.0.0.1:8080
```

- **Linux (amd64)**

```bash
./go-email-extractor-pro-linux-amd64 -config config.json -dashboard 127.0.0.1:8080
```

- **macOS (Intel / amd64)**

```bash
./go-email-extractor-pro-darwin-amd64 -config config.json -dashboard 127.0.0.1:8080
```

- **macOS (Apple Silicon / arm64)**

```bash
./go-email-extractor-pro-darwin-arm64 -config config.json -dashboard 127.0.0.1:8080
```

Open: `http://127.0.0.1:8080`

## Common Flags

- `-config` path to config file
- `-dashboard` dashboard bind address
- `-fresh` start clean (clear checkpoint for this run)
- `-aggressive` increase throughput settings
- `-pull-remote` pull remote checkpoint/output before scan
- `-pull-only` pull remote data and exit
- `-license` custom license file path
- `-license-info` print device ID and exit

## Output Structure

Each run writes to:

`output/<domains-file-stem>/`

Key files:

- `emails.csv`
- `resolved_domains.txt`
- `unresolved_domains.txt`
- `checkpoint_processed.txt`
- `run_summary.json`
- `log.txt`

## Resume and Reliability

- Automatic resume from `checkpoint_processed.txt`
- Run ends automatically when domain queue is drained
- Graceful shutdown on Ctrl+C/SIGTERM with summary writing

## Quality Telemetry

`run_summary.json` includes rejection counters to help tune precision/recall, including:

- `rejected_bad`
- `rejected_disposable_domain`
- `rejected_placeholder_domain`
- `rejected_unwanted_domain`
- `rejected_provider_domain`
- `rejected_role_local_part`
- `rejected_placeholder_local_part`
- `rejected_invalid_shape`
- `rejected_duplicate`
- `rejected_normalize`

## Notes

- If yield is low, review `run_summary.json` and `resolved` vs `unresolved` counts first.
- OCR is optional and increases processing time.
- See `config.example.json` for all tunable parameters.
