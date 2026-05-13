# How to Activate Your License (Buyers)

Your license is **tied to one computer**. Follow these steps to activate.

---

## Step 1 — Get your Device ID

1. Open a terminal in the folder where you installed the extractor.
2. Run the command for your platform:

   **Windows**
   ```
   go-email-extractor-pro.exe -license-info
   ```

   **Linux (amd64)**
   ```
   ./go-email-extractor-pro-linux-amd64 -license-info
   ```

   **macOS (Intel / amd64)**
   ```
   ./go-email-extractor-pro-darwin-amd64 -license-info
   ```

   **macOS (Apple Silicon / arm64)**
   ```
   ./go-email-extractor-pro-darwin-arm64 -license-info
   ```
3. You will see something like:
   ```
   Device ID (send this to obtain a license):
   abc123def456...
   ```
4. **Copy the whole Device ID** (the long line of letters and numbers). That is your machine’s identifier.

---

## Step 2 — Send the Device ID to the seller

- Send the copied **Device ID** to the seller (by email, Telegram, or the channel they gave you).
- They will generate a **license file** for your device and send it to you.

---

## Step 3 — Install your license file

1. The seller will send you a file named **`license.key`**.
2. **Put `license.key` in the same folder as your extractor binary** (`.exe`, Linux, or macOS file).

   Example:
   ```
   C:\YourFolder\
      go-email-extractor-pro.exe
      license.key          ← place it here
      config.json
      ...
   ```

3. Do **not** rename the file; it must be called `license.key`.

---

## Step 4 — Run the program

- Start the extractor as usual (double-click or from the command line).
- If the license is valid, the program will run normally. No extra registration step is needed.

---

## Troubleshooting

| Message | What to do |
|--------|------------|
| **"license invalid or corrupted"** | Make sure `license.key` is in the same folder as your binary and was sent for **your** Device ID. |
| **"license is bound to another device"** | This license was made for a different PC. Use **this computer’s** Device ID (Step 1) and ask the seller for a new license. |
| **"license has expired"** | Contact the seller to renew or extend your license. |
| **"Place license.key next to the executable"** | You need a valid `license.key` in the program folder (see Step 3). |

---

**One license = one computer.** If you use a new PC, run `-license-info` on that PC and request a new license from the seller.
