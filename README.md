
# 📁 File Integrity Monitoring System

**Version:** 1.0

**Name:** Shashikant Patel

**Company:** CODETECH PVT.LTD

**ID:** CTIS7432

**Domain:** Cyber Security & Ethical Hacking
**Duration:** April to May 2026

---

## 📌 Overview

The **File Integrity Monitoring System** is a Python-based utility that tracks and verifies the integrity of files within a specified directory.

It uses **SHA-256 cryptographic hashing** to detect:

* Unauthorized modifications
* Accidental changes
* File additions or deletions

The system creates a baseline of file hashes and compares future scans against it, ensuring a secure audit trail for **security, compliance, and data integrity**.

---

## 🚀 Key Features

* 🔐 **SHA-256 Hashing** – Secure file fingerprinting
* 📊 **Baseline Creation** – Initial snapshot of all files
* 🔍 **Change Detection** – Detects modified, new, and deleted files
* 🗂 **JSON Storage** – Human-readable hash database
* 📄 **PDF Reporting** – Automatic audit report generation

---

## 🏗 System Architecture

### Core Components

* `calculate_hash()` – Computes SHA-256 hash (4KB chunks)
* `scan_files()` – Recursively scans directory
* `load_previous_hashes()` – Loads baseline from JSON
* `save_hashes()` – Saves current hashes
* `compare_hashes()` – Detects file changes
* `generate_pdf()` – Creates audit report

### Data Flow

```
Scan Directory → Calculate Hashes → Load Previous Hashes 
→ Compare → Generate Report → Save New Hashes
```

### File Structure

* `file_hashes.json` → Stores file hashes
* `file_integrity_report.pdf` → Audit report

---

## ⚙️ Installation & Setup

### Requirements

* Python 3.6+
* Libraries:

  * `reportlab`
  * `hashlib` (built-in)
  * `json` (built-in)
  * `datetime` (built-in)
  * `os` (built-in)

### Installation Steps

```bash
pip install reportlab
```

1. Save the script as:

   ```
   file_integrity_monitor.py
   ```

2. Run the script:

```bash
python file_integrity_monitor.py
```

---

## 🔧 Configuration Guide

### Default Variables

```python
MONITOR_DIR = "."
HASH_FILE = "file_hashes.json"
REPORT_PDF_FILE = "file_integrity_report.pdf"
```

### Custom Example

```python
MONITOR_DIR = "/path/to/directory"
HASH_FILE = "custom_hashes.json"
REPORT_PDF_FILE = "custom_report.pdf"
```

---

## ▶️ Usage Instructions

### Basic Usage

```bash
python file_integrity_monitor.py
```

### Workflow

#### 1️⃣ First Run (Baseline Creation)

* Creates initial hash database
* No changes reported

#### 2️⃣ Subsequent Runs

* Detects:

  * Modified files
  * New files
  * Deleted files

#### 3️⃣ Automation

* Use:

  * **cron jobs** (Linux/Mac)
  * **Task Scheduler** (Windows)

---

## 🖥 Console Output Guide

| Status       | Meaning              |
| ------------ | -------------------- |
| `[OK]`       | File unchanged       |
| `[MODIFIED]` | File content changed |
| `[NEW]`      | New file detected    |
| `[DELETED]`  | File removed         |

---

## 📊 Sample Output

### First Run

```
Scanning files...
No previous record found. Creating baseline...

Baseline created successfully.
```

---

### Change Detection

```
[MODIFIED] ./main.py
[NEW] ./backup.zip
[DELETED] ./old_script.py
```

---

### No Changes

```
✔ All files are intact. No changes detected.
```

---

## 📚 API Reference

### `calculate_hash(file_path)`

* Returns SHA-256 hash of a file

### `scan_files(directory)`

* Returns `{file_path: hash}`

### `load_previous_hashes()`

* Loads previous hashes

### `save_hashes(hashes)`

* Saves hashes to JSON

### `compare_hashes(old, new)`

* Returns list of changes

### `generate_pdf(title, content, filename)`

* Generates PDF report

---

## 🛠 Troubleshooting

| Issue                            | Solution                       |
| -------------------------------- | ------------------------------ |
| `ModuleNotFoundError: reportlab` | `pip install reportlab`        |
| Permission denied                | Run with elevated permissions  |
| Missing JSON file                | Normal on first run            |
| Unexpected changes               | Re-run or verify file edits    |
| Slow performance                 | Large directories take time    |
| PDF not generated                | Check permissions & disk space |
| JSON corrupted                   | Delete and regenerate          |

---

## ✅ Best Practices

* 📅 Schedule regular scans
* 📁 Archive PDF reports
* 🚫 Exclude temp/cache files
* 💾 Backup `file_hashes.json`
* 🔍 Review detected changes immediately
* 🔗 Use with Git for code tracking
* 🔐 Secure hash database permissions
* 📂 Monitor critical directories

---

## 📖 Additional Resources

* SHA-256 Hashing
* JSON Format
* ReportLab (PDF generation)

---

## 🎯 Use Cases

* System security monitoring
* Compliance auditing
* Data integrity verification

---

## 📌 License

This project is open-source. Please check the repository for license details.


