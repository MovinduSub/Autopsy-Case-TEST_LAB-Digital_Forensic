# Digital Forensics Investigation – 2020JimmyWilson (CFReDS)

**Tool:** Autopsy Forensic Browser  
**Image:** `2020JimmyWilson.E01`  
**Source:** [CFReDS Portal – DFIR_AB Forensics Image Test image](https://cfreds.nist.gov/all/DFIR_AB/ForensicsImageTestimage)  
**Purpose:** Portfolio demonstration of disk image analysis, virtual disk examination, email artifact recovery, and encrypted container detection using open-source tools.

---

## Case Overview

This investigation examines the forensic disk image `2020JimmyWilson.E01`. The image contains a physical disk with multiple volumes, including a virtual hard disk (`System.vhd`) and a partition labeled **J. Wilson**.  

Key areas of interest include:
- System and user account information related to Jimmy Wilson
- Email artifacts
- Presence of encrypted containers (TrueCrypt)
- Partition and volume analysis

---

## Tools Used

| Tool              | Version     | Purpose                                      |
|-------------------|-------------|----------------------------------------------|
| Autopsy           | 4.x         | Primary analysis platform                    |
| The Sleuth Kit    | Bundled     | File system, volume & metadata analysis      |
| Hash utilities    | -           | Evidence integrity verification              |

---

## Evidence Integrity

| Item                        | Algorithm | Hash Value                                      |
|-----------------------------|-----------|-------------------------------------------------|
| 2020JimmyWilson.E01         | MD5       | `4193CC3BC7111DDF8BE7A00677F2A2F4`              |
| 2020JimmyWilson.E01         | SHA-256   | *(paste your calculated value here)*            |

Hashes were calculated before analysis and verified after adding the image as a data source in Autopsy.

---

## Methodology

1. **Hash Verification** – Calculated MD5 and SHA-256 of the original E01 image.
2. **Case Creation** – Created a new single-user case in Autopsy.
3. **Data Source Addition** – Added `2020JimmyWilson.E01` and selected relevant ingest modules.
4. **Ingest** – Ran File Type Identification, Recent Activity, Keyword Search, Hash Lookup, Extension Mismatch Detector, Embedded File Extractor, and PhotoRec Carver.
5. **Analysis** – Examined partitions, virtual disks (`System.vhd`), user accounts, email artifacts, and encrypted volumes.
6. **Documentation** – Tagged key items, captured screenshots, and generated reports.

---

## Key Findings

### 1. Disk Structure
- Physical disk contains multiple volumes.
- One volume contains a virtual hard disk: **System.vhd**.
- A partition labeled **J. Wilson** was identified (associated with TrueCrypt-related content).

### 2. User & System Information
- Primary user context linked to **Jimmy Wilson**.
- Email address associated with the user: `wilsonjimmy807@gmail.com`.

### 3. Email Artifacts
- Multiple email messages recovered (example: `447018D5-00000006.eml`).
- Timezone offset analysis performed on received emails.
- Sender and recipient details documented.

### 4. Encrypted Containers
- TrueCrypt-related directories and artifacts located on the **J. Wilson** volume.
- Indicates possible use of encrypted storage.

## Screenshots

Key stages of the investigation are documented in the `/screenshots` folder:

- Case creation and data source addition
- Ingest module selection
- Partition / volume view
- System.vhd examination
- J. Wilson partition
- Email artifacts
- TrueCrypt-related findings
- Timeline and final report generation

---

## Reports

- Formal written report: [`reports/formal-report.md`](reports/formal-report.md)
- Autopsy-generated HTML report (exported)

---

## Lessons Learned

- Virtual hard disks (VHD) embedded inside physical images require careful volume analysis.
- Partition labels and TrueCrypt artifacts can reveal intentional 

## Disclaimer

This repository is for educational and portfolio purposes only.  
The original forensic image belongs to the CFReDS / NIST collection.  
No actual evidence files are included in this repository.

---

**Analyst:** [Movindu Subasinghe]  
**Date of Analysis:** [2026-11-05]  
**Autopsy Version:** [4.22.1]