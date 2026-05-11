# Go Email Extractor Pro

## Get started

**1. Activate**  
- **Windows:** `go-email-extractor-pro.exe -license-info`  
- **Linux:** `./go-email-extractor-pro-linux-amd64 -license-info`  
- **Mac (Intel):** `./go-email-extractor-pro-darwin-amd64 -license-info`  
- **Mac (Apple Silicon):** `./go-email-extractor-pro-darwin-arm64 -license-info`  
Send the Device ID to the seller. Put the file they send you (**license.key**) in this folder.  
More help: **LICENSE_ACTIVATION.md**

**2. Set up**  
- Copy **config.example.json** → **config.json**  
- Put your domains in **domains/domains.txt** (one domain per line)

**3. Run**  
- **Windows** (Command Prompt or PowerShell):
  ```
  go-email-extractor-pro.exe -config config.json -dashboard 127.0.0.1:8080
  ```
- **Linux:** `chmod +x go-email-extractor-pro-linux-amd64` then:
  ```
  ./go-email-extractor-pro-linux-amd64 -config config.json -dashboard 127.0.0.1:8080
  ```
- **Mac (Intel):** `chmod +x go-email-extractor-pro-darwin-amd64` then:
  ```
  ./go-email-extractor-pro-darwin-amd64 -config config.json -dashboard 127.0.0.1:8080
  ```
- **Mac (Apple Silicon):** `chmod +x go-email-extractor-pro-darwin-arm64` then:
  ```
  ./go-email-extractor-pro-darwin-arm64 -config config.json -dashboard 127.0.0.1:8080
  ```

Then open **http://127.0.0.1:8080** in your browser. You’ll see progress and can export emails to CSV.

---

## Personalize config

**config.json** is just a text file. Open it and change what you need:

- **domains_file_path** — where your domain list lives (default: `./domains/domains.txt`)
- **output_directory** — where results are saved (default: `output`)
- **concurrency** — how many domains at once (default 100; higher = faster, more CPU)
- **rate_limit_per_second** — max requests per second (default 200)
- **max_contact_pages_per_domain** / **max_pages_per_domain** — how deep to crawl (defaults 30 and 50)
- **enable_ocr** — set to `true` to get emails from images. **You must download and install Tesseract** on your system first (e.g. [tesseract-ocr.github.io](https://tesseract-ocr.github.io) or your package manager); without it, OCR will not work.

Save the file and run the same command again. No need to restart anything.

---

Support: Telegram @dranach · One license = one computer.
