**Encrypted File Backup Tool** (BYOW Project)

A lightweight, AES-GCM–based encrypted backup system built for the Build Your Own HW (BYOW) security engineering assignment.
This project includes a full Google Colab notebook, working prototype code, security evaluation, and documentation.

📌**Project Overview**

This project demonstrates a secure file-backup workflow using authenticated encryption (AEAD).

It is designed as a teaching/demo tool illustrating:

1.Symmetric encryption using AES-256-GCM
2.Integrity protection via AEAD authentication tags
3.Secure nonce handling
4.Tamper detection
5.Optional alternative algorithm: ChaCha20-Poly1305
6.Simple file-based backup simulation

This prototype runs in Google Colab, making it easy to execute without local setup.

🚀**Features**

Core
🔐 AES-256-GCM encryption (confidentiality + integrity)
🔄 File encryption/decryption workflow
🧪 Tamper detection: modified ciphertext fails to decrypt
🔑 Random key generation using cryptographic-safe entropy

Optional Module
⚙️ ChaCha20-Poly1305 encryption (fast on devices without AES acceleration)

🛠️ **How to Run (in Google Colab)**

Open the notebook directly

Upload the notebook to Google Colab :
Go to https://colab.research.google.com/

Choose Upload Notebook :
Select BYOW_Backup_Tool.ipynb

Run all cells (Runtime → Run all)

🔍 **Security Model**

✔ Guarantees
Confidentiality: AES-256-GCM protects the file contents
Integrity: AEAD tag ensures tampering is detected
Unique nonce per file: Prevents catastrophic GCM misuse

⚠ **Limitations**

Keys are stored in memory only (no secure keystore)
Not designed for large-scale production workloads
Nonce management is simple (random, not streaming)
No user authentication model (focus is on encryption only)
No network transmission layer included (local backup only)

🧪 **Test Summary**


Test	Expected	Result
Encrypt → Decrypt	Plaintext restored correctly	✔ PASS
Tamper ciphertext	Decryption fails	✔ PASS
Nonce uniqueness	Nonces should be unique per file	✔ PASS (random per encryption)
