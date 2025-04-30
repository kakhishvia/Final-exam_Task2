
# Task 2 – Secure File Exchange Using RSA + AES

## 🔐 Overview
This task demonstrates secure file transfer using hybrid encryption:
- AES-256 is used to encrypt the actual file.
- RSA is used to encrypt the AES key.

---

## 🔄 Encryption & Decryption Flow

### 🔹 Bob:
1. Generates RSA key pair → `private.pem`, `public.pem`

### 🔹 Alice:
2. Creates a message in `alice_message.txt`
3. Generates AES-256 key and IV
4. Encrypts file using AES-CBC → `encrypted_file.bin`
5. Encrypts AES key with Bob’s RSA public key → `aes_key_encrypted.bin`

### 🔹 Bob:
6. Decrypts AES key with RSA private key
7. Decrypts the file using AES key and IV → `decrypted_message.txt`
8. Compares SHA-256 hashes to verify integrity

---

## 📂 Files Submitted

- `alice_message.txt` – original plaintext  
- `encrypted_file.bin` – AES-encrypted file  
- `aes_key_encrypted.bin` – RSA-encrypted AES key  
- `decrypted_message.txt` – decrypted output  
- `private.pem`, `public.pem` – Bob's RSA key pair  
- `README.md` – this file  
