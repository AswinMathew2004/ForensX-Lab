# 📖 ForensX Lab — Complete Usage Guide

## Table of Contents

1. [Getting Started](#-getting-started)
2. [Dashboard](#-dashboard)
3. [Hash Calculator](#-hash-calculator)
4. [Hex Viewer](#-hex-viewer)
5. [Metadata Extractor](#-metadata-extractor)
6. [File Signature Analyzer](#-file-signature-analyzer)
7. [String Extractor](#-string-extractor)
8. [Hash Comparator](#️-hash-comparator)
9. [Base64 Codec](#-base64-codec)
10. [Entropy Analysis](#-entropy-analysis)
11. [Steganography Detector](#️-steganography-detector)
12. [Case Information](#-case-information)
13. [Chain of Custody](#-chain-of-custody)
14. [Evidence Log](#️-evidence-log)
15. [Timeline Analyzer](#️-timeline-analyzer)
16. [Report Generator](#-report-generator)
17. [ACPO Guidelines](#-acpo-guidelines)
18. [Recommended Workflow](#-recommended-investigation-workflow)
19. [Keyboard Shortcuts & Tips](#-tips--tricks)
20. [FAQ](#-faq)

---

## 🚀 Getting Started

### Option A — Use Online (GitHub Pages)
1. Visit your hosted URL: `https://yourusername.github.io/forensx-lab`
2. The app loads instantly — no installation needed
3. Start using any tool from the sidebar

### Option B — Run Locally (Offline)
1. Download `index.html` from the repository
2. Double-click the file to open in any browser (Chrome/Firefox/Edge)
3. Works 100% offline — no internet required after download

### Option C — Host on Your Server
1. Copy `index.html` to your web server's root directory
2. Access via your domain — that's it, single file deployment

### Interface Overview
```
┌──────────────────────────────────────────────┐
│  Header Bar (Logo, Status, Website link)     │
├──────────┬───────────────────────────────────┤
│          │                                   │
│ Sidebar  │         Main Content Area         │
│  (Tool   │   (Selected tool loads here)      │
│   List)  │                                   │
│          │                                   │
├──────────┴───────────────────────────────────┤
│  Mobile Navigation (phones/tablets only)     │
└──────────────────────────────────────────────┘
```
- Click any tool in the **sidebar** to switch views
- On mobile, use the **bottom navigation bar**
- All actions are **automatically logged** in the Timeline

---

## 📊 Dashboard

**What it does:** Central overview of your investigation.

**How to use:**
- See live counts of evidence items, hashes computed, and chain of custody entries
- View case status at a glance
- Use **Quick Actions** buttons to jump to commonly used tools
- The ACPO Principles are displayed as a quick reference

**When to use:** Start here at the beginning of every session to get oriented.

---

## 🔐 Hash Calculator

**What it does:** Computes cryptographic hashes (MD5, SHA-1, SHA-256, SHA-512) for any file or text.

**Why it matters:** Hash values are the foundation of digital evidence integrity. They prove a file hasn't been modified.

### Hash a File
1. Click **Hash Calculator** in the sidebar
2. **Drag and drop** a file onto the drop zone, OR click to browse
3. Wait for computation (progress bar shows status)
4. View all 4 hash values: MD5, SHA-1, SHA-256, SHA-512
5. Click **Copy SHA-256** to copy the hash
6. Click **Add to Evidence** to register the file in your evidence log

### Hash Text
1. Scroll down to the **Text Hash** section
2. Type or paste any text
3. Click **Compute Hash**
4. All 4 hash values appear instantly

### Hash History
- Every file you hash is saved in the Hash History section
- History persists during your session
- Use this to track all files you've processed

**Pro tip:** Always hash evidence **before** and **after** analysis to prove you didn't alter it.

---

## 🔍 Hex Viewer

**What it does:** Displays raw binary content of any file in hexadecimal format with ASCII representation.

**Why it matters:** Lets you see exactly what's inside a file at the byte level — essential for finding hidden data, verifying file headers, and spotting anomalies.

### How to Use
1. Click **Hex Viewer** in the sidebar
2. Select how many rows to display (64 to 1024)
3. Drag and drop a file onto the drop zone
4. View the three-column display:
   - **Offset** (green) — byte position in the file
   - **Hex Bytes** — raw hexadecimal values
   - **ASCII** — readable character representation (dots for non-printable)

### Reading the Display
```
Offset     Hex Bytes                                    ASCII
00000000   89 50 4E 47 0D 0A 1A 0A 00 00 00 0D 49 48   .PNG........IH
```
- The offset `00000000` means this is the start of the file
- `89 50 4E 47` = PNG file signature (magic bytes)
- ASCII column shows readable characters where possible

**Pro tip:** The first few bytes (magic bytes) tell you the real file type regardless of extension.

---

## 📋 Metadata Extractor

**What it does:** Extracts all available metadata from any file — properties, EXIF data (images), file signatures, and entropy analysis.

### How to Use
1. Click **Metadata Extractor** in the sidebar
2. Drop a file onto the zone
3. View extracted data including:
   - File name, size, MIME type
   - Last modified date
   - File signature (true file type)
   - Shannon entropy score
   - **For images:** dimensions, megapixels, color type, bit depth
4. Click **Copy Metadata** to save all data
5. Click **Add to Evidence** to register

### Understanding Entropy
| Entropy Range | Meaning |
|---------------|---------|
| 0.0 – 6.0 🟢 | Structured data (text, documents) |
| 6.0 – 7.5 🟡 | Mixed content (docs with images) |
| 7.5 – 8.0 🔴 | Encrypted or compressed data |

---

## 🧬 File Signature Analyzer

**What it does:** Identifies the TRUE file type by reading magic bytes — regardless of what the file extension says.

**Why it matters:** Attackers often rename files (e.g., hiding an `.exe` as `.jpg`). This tool catches that.

### How to Use
1. Click **File Signatures** in the sidebar
2. Drop a file onto the zone
3. View results:
   - **Detected Type** — what the file actually is
   - **Extension Match** — ✅ if extension matches, ⚠️ MISMATCH if it doesn't
   - **Magic Bytes** — the raw hex signature

### What a Mismatch Means
- **Red MISMATCH warning** = the file extension doesn't match its real type
- This could indicate: file renaming, deliberate obfuscation, corruption, or tampering
- Always investigate mismatches — they're forensically significant

### Reference Table
The bottom panel shows common file signatures for quick reference (JPEG, PNG, PDF, ZIP, EXE, etc.)

---

## 📝 String Extractor

**What it does:** Extracts readable ASCII text strings from any binary file.

**Why it matters:** Hidden URLs, email addresses, file paths, passwords, and other text evidence can be found inside executables, images, and other binary files.

### How to Use
1. Click **String Extractor** in the sidebar
2. Set **Minimum String Length** (4, 6, 8, or 12 characters)
3. Drop a file onto the zone
4. View categorized results:
   - **🌐 URLs** — any web addresses found
   - **📧 Emails** — any email addresses found
   - **📁 Paths** — any file/folder paths found
   - **All Strings** — complete list with hex offsets

### Reading Results
```
0x00001A3F  https://example.com/upload
0x0000234B  admin@company.com
0x00003100  C:\Users\suspect\Documents\secret.docx
```
- Left column = byte offset where the string was found
- Right column = the extracted string

**Pro tip:** Use minimum length 4 for thorough extraction, or 8+ to filter noise from binary files.

---

## ⚖️ Hash Comparator

**What it does:** Compares two hash values to verify if evidence has been modified.

**Why it matters:** Under ACPO Principle 1, you must prove evidence data hasn't changed. Hash comparison is the standard method.

### How to Use
1. Click **Hash Comparator** in the sidebar
2. Paste the **original/known hash** in the first field
3. Paste the **evidence copy hash** in the second field
4. Click **Compare Hashes**
5. Results show:
   - **✅ MATCH** — evidence integrity is verified
   - **❌ MISMATCH** — data may have been tampered with

### Typical Workflow
1. Hash the original evidence → save the hash
2. Create a forensic copy
3. Hash the copy
4. Compare both hashes — they MUST match

---

## 🔄 Base64 Codec

**What it does:** Encodes text/data to Base64, or decodes Base64 back to readable text.

**Why it matters:** Base64 encoding is commonly used to hide data in emails, web traffic, malware configurations, and scripts.

### How to Use
- **Encode:** Paste text → click **Encode →** → get Base64 output
- **Decode:** Paste Base64 string → click **← Decode** → get readable text
- **From File:** Click **📂 From File** → select any file → get its Base64 representation
- Click **📋 Copy Output** to copy results

### Common Forensic Uses
- Decoding suspicious email attachments
- Analyzing encoded commands in malware
- Converting binary evidence for text-based reports
- Examining encoded web traffic payloads

---

## 📈 Entropy Analysis

**What it does:** Calculates Shannon entropy to measure randomness in file data, displayed as an overall score and visual block chart.

**Why it matters:** Encrypted files have near-maximum entropy (~8.0). This helps you detect encryption, compression, hidden payloads, and packed malware.

### How to Use
1. Click **Entropy Analysis** in the sidebar
2. Drop a file onto the zone
3. View results:
   - **Overall Entropy** — single score out of 8.0
   - **Randomness %** — percentage representation
   - **Assessment** — High/Medium/Low classification
   - **Block Chart** — visual entropy per 1KB block (red=high, orange=medium, green=low)

### Reading the Block Chart
```
█ █ █ ▄ ▄ █ █ █ █ █ █ █ █ ▂ ▂ ▂ ▂ █ █ █
 ↑ High entropy section    ↑ Low section   ↑ High again
   (encrypted/compressed)   (headers/text)   (encrypted)
```
- Sudden drops in entropy = file headers, metadata, or unencrypted sections
- Uniformly high entropy = likely encrypted or compressed throughout

---

## 🖼️ Steganography Detector

**What it does:** Analyzes images for signs of hidden data (steganography).

### How to Use
1. Click **Stego Detector** in the sidebar
2. Drop an **image file** (JPEG, PNG, BMP, GIF)
3. View the risk assessment:
   - **Risk Level:** HIGH / MEDIUM / LOW
   - **Findings table** with specific indicators

### What It Checks
| Check | What It Means |
|-------|---------------|
| **Appended data after EOI/IEND** | Data hidden after the image's end marker |
| **LSB distribution** | Least Significant Bit uniformity suggests LSB steganography |
| **High entropy** | May indicate encrypted hidden payload |
| **Oversized file** | Image is larger than expected for its dimensions |

### Risk Levels
- **HIGH 🔴** — Strong indicators of hidden data (appended bytes, data after end markers)
- **MEDIUM 🟡** — Suspicious patterns (unusual LSB ratio, high entropy)
- **LOW 🟢** — No obvious indicators detected

---

## 📁 Case Information

**What it does:** Define and store your investigation case details.

### How to Use
1. Click **Case Information** in the sidebar
2. Fill in all fields:
   - **Case Number** — your reference (e.g., `DF-2026-0042`)
   - **Case Title** — descriptive name
   - **Lead Examiner** — your name and credentials
   - **Organization** — your department/company
   - **Date Opened** — when the investigation started
   - **Status** — Open / In Progress / Under Review / Closed
   - **Description** — brief case summary
   - **Legal Authority** — warrant or authorization reference
3. Click **💾 Save Case Information**

**Do this FIRST** — case info appears in all generated reports and the dashboard.

---

## 🔗 Chain of Custody

**What it does:** Records every interaction with evidence — who handled it, when, where, and what was done.

**Why it matters:** ACPO Principle 3 requires a complete audit trail. Without proper chain of custody, evidence may be inadmissible in court.

### How to Use
1. Click **Chain of Custody** in the sidebar
2. Fill in the entry form:
   - **Evidence Item ID** — which evidence (e.g., `EV-001`)
   - **Date & Time** — when the action occurred
   - **Action** — what was done (Received, Acquired Image, Transferred, Analyzed, etc.)
   - **Handled By** — who performed the action
   - **Location** — where it happened
   - **Notes** — detailed description
3. Click **➕ Add Entry**
4. Entry appears in the log table below

### Actions Available
| Action | When to Use |
|--------|-------------|
| Received | Evidence first obtained |
| Acquired Image | Forensic copy created |
| Transferred | Evidence moved between people/locations |
| Analyzed | Examination performed |
| Stored | Placed in secure storage |
| Returned | Given back to owner/authority |
| Sealed / Unsealed | Evidence bag sealed or opened |
| Copied | Additional copy made |
| Verified Hash | Integrity check performed |

---

## 🗄️ Evidence Log

**What it does:** Central registry of all evidence items in your investigation.

### How to Use

#### Manual Entry
1. Click **Evidence Log** in the sidebar
2. Fill in details:
   - **Evidence ID** — auto-generated if blank (EV-001, EV-002, etc.)
   - **Description** — what the evidence is
   - **Type** — Hard Drive, USB, Mobile Device, File, etc.
   - **Source** — where it came from
   - **SHA-256 Hash** — paste the hash for integrity
   - **Notes** — serial numbers, condition, etc.
3. Click **➕ Add Evidence**

#### Auto-Registration
When using the Hash Calculator or Metadata Extractor, click the **🗄️ Add to Evidence** button to automatically register the file with its hash.

---

## ⏱️ Timeline Analyzer

**What it does:** Automatic audit trail that logs every action performed across all tools.

### How to Use
1. Click **Timeline Analyzer** in the sidebar
2. View the chronological log of all activities:
   - Timestamp of each action
   - Which tool was used
   - What was done
3. Use **Clear** to reset (careful — this deletes the audit trail)

### Auto-Logged Activities
Every tool automatically logs its actions:
- Files hashed, hex viewed, metadata extracted
- Signatures analyzed, strings extracted
- Hash comparisons, entropy analysis
- Evidence registered, CoC entries added
- Reports generated

**Pro tip:** Never clear the timeline during an active investigation — it's your ACPO Principle 3 compliance proof.

---

## 📄 Report Generator

**What it does:** Generates a comprehensive, court-admissible forensic investigation report.

### How to Use
1. Click **Report Generator** in the sidebar
2. Review the summary (evidence count, CoC entries, timeline events)
3. Select **Report Format:**
   - **HTML** — formatted, printable, professional layout
   - **Plain Text** — simple text file
4. Add your **Findings & Conclusions** in the text area
5. Click **📄 Generate Report**
6. The report downloads automatically

### Report Contents (Automatically Included)
- **Case Information** — all details from Case Info setup
- **ACPO Compliance Statement** — principle-by-principle verification
- **Evidence Register** — all logged evidence with hashes
- **Chain of Custody** — complete handling log
- **Hash Verification Log** — every hash computation
- **Investigation Timeline** — full audit trail
- **Findings & Conclusions** — your written analysis
- **Signature Blocks** — for examiner and reviewer

### Printing as PDF
1. Generate the HTML report
2. Open the downloaded `.html` file in Chrome
3. Press **Ctrl + P** (or Cmd + P on Mac)
4. Select **Save as PDF** as the printer
5. Click **Save** — you now have a professional PDF report

---

## 📖 ACPO Guidelines

**What it does:** Reference page for the four ACPO principles with implementation guidance.

Includes a step-by-step **Best Practices Checklist** mapping each investigation phase to the right ForensX tool.

---

## 🔄 Recommended Investigation Workflow

Follow this order for a proper forensic investigation:

```
Step 1: Case Setup
    └─→ Fill Case Information (case number, examiner, legal authority)

Step 2: Evidence Receipt
    └─→ Log in Evidence Log (description, type, source)
    └─→ Add Chain of Custody entry ("Received")

Step 3: Evidence Acquisition
    └─→ Hash original evidence (Hash Calculator)
    └─→ Create forensic copy (use external imaging tool)
    └─→ Hash the copy
    └─→ Compare hashes (Hash Comparator) → must match
    └─→ Add CoC entry ("Acquired Image")

Step 4: Analysis
    └─→ File Signature check (verify true file types)
    └─→ Metadata extraction (dates, dimensions, properties)
    └─→ Hex Viewer (inspect raw binary content)
    └─→ String Extraction (find hidden text, URLs, emails)
    └─→ Entropy Analysis (detect encryption)
    └─→ Steganography Detection (check images for hidden data)
    └─→ Add CoC entry ("Analyzed") for each step

Step 5: Post-Analysis Verification
    └─→ Re-hash evidence copy
    └─→ Compare with Step 3 hash → must still match
    └─→ Add CoC entry ("Verified Hash")

Step 6: Reporting
    └─→ Write findings and conclusions
    └─→ Generate Report (HTML format)
    └─→ Print to PDF
    └─→ Add CoC entry ("Report Generated")
```

---

## 💡 Tips & Tricks

- **Drag & Drop everywhere** — all file input zones accept drag and drop
- **Copy any hash** — click the copy button next to hash results
- **Auto-evidence** — use "Add to Evidence" buttons in Hash Calculator and Metadata Extractor
- **Session persistence** — your data stays as long as the browser tab is open
- **Print reports** — open HTML report in browser → Ctrl+P → Save as PDF
- **Mobile friendly** — use the bottom nav bar on phones and tablets
- **Works offline** — once loaded, no internet connection needed
- **No data uploaded** — everything processes locally in your browser

---

## ❓ FAQ

**Q: Is my data safe?**
A: Yes. Everything runs in your browser. No files are uploaded anywhere. No server, no cloud, no tracking.

**Q: Does it work offline?**
A: Yes. After the first page load, the tool works completely offline.

**Q: Can I use this for real investigations?**
A: This tool is designed for education, training, and basic forensic triage. For court-admissible work, combine with industry-standard tools (EnCase, FTK, Autopsy) and follow your jurisdiction's legal requirements.

**Q: What browsers are supported?**
A: Chrome 90+, Firefox 88+, Edge 90+, Safari 15+, and their mobile versions.

**Q: How do I save my work?**
A: Generate a report before closing the tab. Session data is lost when you close the browser.

**Q: Can multiple people use it simultaneously?**
A: Yes, each person's instance runs independently in their own browser.

**Q: Is the MD5 hash accurate?**
A: Yes. The tool uses a full JavaScript MD5 implementation and the Web Crypto API for SHA hashes.

---

## 📬 Support

- **Website:** [aswinmathew.xyz](https://aswinmathew.xyz)
- **Issues:** Open a GitHub Issue on the repository
- **License:** MIT — free to use, modify, and distribute

---

*ForensX Lab v1.0 — Built by [Aswin Mathew](https://aswinmathew.xyz)*
