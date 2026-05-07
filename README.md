# 🔬 ForensX Lab — Digital Forensics & Evidence Preservation

[![Live Demo](https://img.shields.io/badge/Live-Demo-00ff88?style=for-the-badge)](https://forens-x-lab.vercel.app/)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![ACPO](https://img.shields.io/badge/ACPO-Compliant-green?style=for-the-badge)]()

> **An all-in-one, browser-based digital forensics toolkit for evidence acquisition, analysis, and court-admissible report generation — following ACPO chain of custody guidelines.**

**Author:** [Aswin Mathew](https://aswinmathew.xyz)

---

## 🚀 Features

### 🔐 Acquisition Tools
- **Hash Calculator** — MD5, SHA-1, SHA-256, SHA-512 for files & text
- **Hex Viewer** — Binary inspection with hex dump + ASCII view
- **Metadata Extractor** — File properties, EXIF/image data extraction
- **File Signature Analyzer** — Magic bytes detection for true file type verification
- **String Extractor** — ASCII string extraction with URL, email & path detection

### 🔍 Analysis Tools
- **Hash Comparator** — Evidence integrity verification through hash comparison
- **Base64 Codec** — Encode/decode Base64 data
- **Entropy Analysis** — Shannon entropy for encryption/compression detection
- **Steganography Detector** — LSB analysis, appended data detection, entropy profiling

### 📄 Reporting & Chain of Custody
- **Case Management** — Full case information setup
- **Chain of Custody Log** — ACPO-compliant evidence handling records
- **Evidence Registry** — Central evidence log with hash tracking
- **Timeline / Audit Trail** — Automatic activity logging for all tools
- **Report Generator** — Court-admissible HTML/Text forensic reports with signatures

### 📖 Reference
- **ACPO Guidelines** — Full 4-principle reference with implementation checklist

---

## 🛡️ Privacy & Security

**100% Client-Side Processing** — No data leaves your browser. Ever.

- ✅ No server-side processing
- ✅ No file uploads to external services
- ✅ No cookies, tracking, or analytics
- ✅ Works completely offline after first load
- ✅ Safe for handling sensitive investigation data

---

## 📦 Deployment (Free on GitHub Pages)

### Quick Setup (5 minutes)

1. **Fork or clone this repository:**
   ```bash
   git clone https://github.com/yourusername/forensx-lab.git
   cd forensx-lab
   ```

2. **Push to your GitHub account:**
   ```bash
   git remote set-url origin https://github.com/yourusername/forensx-lab.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to your repo → **Settings** → **Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** → **/ (root)**
   - Click **Save**

4. **Access your live site:**
   ```
   https://yourusername.github.io/forensx-lab/
   ```

### Alternative: Download & Run Locally

Just download `index.html` and open it in any modern browser. That's it — no build tools, no dependencies, no server needed.

---

## 💻 Compatibility

| Browser | Status |
|---------|--------|
| Chrome 90+ | ✅ Full Support |
| Firefox 88+ | ✅ Full Support |
| Edge 90+ | ✅ Full Support |
| Safari 15+ | ✅ Full Support |
| Mobile Chrome/Safari | ✅ Responsive UI |

**Requirements:** Modern browser with Web Crypto API support (all current browsers).

---

## 🔬 ACPO Compliance

This tool follows the **Association of Chief Police Officers (ACPO) Good Practice Guide for Digital Evidence**:

| Principle | Description | How ForensX Implements It |
|-----------|-------------|--------------------------|
| **1** | No action should change evidence data | All processing is read-only on forensic copies |
| **2** | Accessing original data requires competency | Tool provides guidance and reference materials |
| **3** | Audit trail must be maintained | Automatic timeline logging of all activities |
| **4** | Investigation lead has overall responsibility | Case management with examiner designation |

---

## 📋 Use Cases

- **Digital Forensic Investigations** — Analyze files, verify integrity, document chain of custody
- **Incident Response** — Quick file triage, hash verification, string extraction
- **Cybersecurity Training** — Learn forensic methodology with hands-on tools
- **Academic Projects** — Demonstrate digital forensics concepts
- **Evidence Processing** — Generate court-admissible documentation

---

## 🏗️ Architecture

```
forensx-lab/
├── index.html          # Single-file application (HTML + CSS + JS)
├── README.md           # This file
└── LICENSE             # MIT License
```

**Zero dependencies. Zero build step. One file.**

The entire application is contained in a single `index.html` file using:
- Vanilla JavaScript (no frameworks)
- Web Crypto API for cryptographic hashing
- CSS Grid/Flexbox for responsive layout
- FileReader API for local file processing

---

## 🤝 Contributing

Contributions welcome! Ideas for expansion:

- [ ] NTFS/FAT filesystem parser
- [ ] Registry hive viewer
- [ ] Email header analyzer
- [ ] Network packet parser (PCAP)
- [ ] Memory dump analyzer
- [ ] Disk image mounting (dd/E01)
- [ ] PDF metadata deep extraction
- [ ] EXIF GPS coordinate mapping
- [ ] Multi-language support

---

## 📜 License

MIT License — See [LICENSE](LICENSE) for details.

---

## 👤 Author

**Aswin Mathew**  
🌐 [aswinmathew.xyz](https://aswinmathew.xyz)

---

<p align="center">
  <strong>⚠️ Disclaimer:</strong> This tool is for educational and legitimate forensic purposes only. 
  Always follow applicable laws and obtain proper authorization before examining digital evidence.
</p>
