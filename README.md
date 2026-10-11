# Aman — Local file safety check

Aman is a browser-based file inspection prototype for the **Digital Trust & Cyber-Secure Nation** theme. Choose or drop in a file to check it locally for selected warning signs before opening it.

## Run it

Open `index.html` in a modern browser. There is no build step, package installation, backend, or API key.

## What the check does

- Reads a file selected by the user in the browser, with a 50 MB size limit.
- Compares common file extensions with recognizable file headers.
- Flags deceptive double extensions, executable and macro-enabled file types, and selected suspicious script or PDF patterns.
- Reads ZIP central-directory entry names without extracting contents; can flag executable or script files, macro project markers, encrypted entries, unusual paths, and extreme expansion sizes.
- Gives suggested next steps based on the findings.
- Calculates a SHA-256 fingerprint for the full file when browser cryptography is available.
- Shows findings and recent scan summaries in the current page session.

The app does not upload the file, save the file, or execute it. Scan summaries exist only in page memory and disappear when the page is closed.

- Shows a 0–100 rule-weighted risk score with green, yellow, orange, and red bands; the score is an indicator, not a probability.

## Important limitations

This is a **basic heuristic check**, not antivirus software and not a malware verdict. A warning can be a false positive, and a clean result does not prove a file is safe. The prototype does not extract or inspect archive contents, unpack encrypted files, inspect every file format or the full contents of every large file, use a malware signature database, or verify reputation with an external service. Archive checks only review directory metadata and can miss threats inside files. Keep your operating system security software enabled, and only open files from sources you trust.

For production malware protection, integrate a maintained scanning engine or trusted threat-intelligence service on a secure backend, with explicit consent, privacy controls, safe file handling, and clear reporting of scan coverage.
