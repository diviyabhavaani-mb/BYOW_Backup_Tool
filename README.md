Encrypted File Backup Tool (BYOW Project)

A lightweight, AES-GCM–based encrypted backup system built for the Build Your Own HW (BYOW) security engineering assignment.
This project includes a full Google Colab notebook, working prototype code, security evaluation, and documentation.

📌 Project Overview

This project demonstrates a secure file-backup workflow using authenticated encryption (AEAD).
It is designed as a teaching/demo tool illustrating:

Symmetric encryption using AES-256-GCM

Integrity protection via AEAD authentication tags

Secure nonce handling

Tamper detection

Optional alternative algorithm: ChaCha20-Poly1305

Simple file-based backup simulation

This prototype runs in Google Colab, making it easy to execute without local setup.

📁 Files in This Repository
File	Description
BYOW_Backup_Tool_Colab.ipynb	Main Colab notebook containing code, explanations, and tests
BYOW_Backup_Tool_Report_Detailed.pdf	Detailed project report (design → evaluation)
BYOW_Backup_Tool_Report.pdf	Shorter 1–2 page report
README.md	Project documentation (this file)
sample.txt (generated at runtime)	Example input file created in notebook
*.enc	Encrypted file outputs (AES-GCM or ChaCha20-Poly1305)
🚀 Features
Core

🔐 AES-256-GCM encryption (confidentiality + integrity)

🔄 File encryption/decryption workflow

🧪 Tamper detection: modified ciphertext fails to decrypt

🔑 Random key generation using cryptographic-safe entropy

Optional Module

⚙️ ChaCha20-Poly1305 encryption (fast on devices without AES acceleration)

🛠️ How to Run (in Google Colab)
Option 1: Open the notebook directly

Upload the notebook to Google Colab:

Go to https://colab.research.google.com/

Choose Upload Notebook

Select BYOW_Backup_Tool_Colab.ipynb

Run all cells (Runtime → Run all)

Option 2: GitHub Integration

If you push this repo to GitHub, you can open it directly:

https://colab.research.google.com/github/<your_username>/<repo_name>/blob/main/BYOW_Backup_Tool_Colab.ipynb

Notebook Workflow

The notebook runs through:

Install dependencies (cryptography)

Generate AES key

Create a sample plaintext file

Encrypt the file → produce sample.txt.enc

Decrypt the encrypted file

Tamper with ciphertext to show integrity failure

Run optional ChaCha20-Poly1305 encryption/decryption

🔍 Security Model
✔ Guarantees

Confidentiality: AES-256-GCM protects the file contents

Integrity: AEAD tag ensures tampering is detected

Unique nonce per file: Prevents catastrophic GCM misuse

⚠ Limitations (Expected for a Student Prototype)

Keys are stored in memory only (no secure keystore)

Not designed for large-scale production workloads

Nonce management is simple (random, not streaming)

No user authentication model (focus is on encryption only)

No network transmission layer included (local backup only)


🧪 Test Summary
Test	Expected	Result
Encrypt → Decrypt	Plaintext restored correctly	✔ PASS
Tamper ciphertext	Decryption fails	✔ PASS
Nonce uniqueness	Nonces should be unique per file	✔ PASS (random per encryption)
