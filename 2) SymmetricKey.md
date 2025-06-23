#  Symmetric Key Cryptography
Symmetric key cryptography uses the same secret key for both encryption and decryption.
### 🧊 Block Ciphers
Block ciphers encrypt data in fixed-size blocks, typically 64 or 128 bits.
| Algorithm | Description                          |
| --------- | ------------------------------------ |
| **DES**   | Outdated, uses 56-bit keys           |
| **AES**   | Modern, secure (128/192/256-bit key) |
### 📦 Block Cipher Modes
| Mode                            | Description                                         |
| ------------------------------- | --------------------------------------------------- |
| **ECB** (Electronic Codebook)   | Each block encrypted independently (weak)           |
| **CBC** (Cipher Block Chaining) | Each block XOR’d with the previous ciphertext block |
| **CTR** (Counter Mode)          | Turns block cipher into stream cipher               |
| **GCM** (Galois/Counter Mode)   | Adds integrity/authentication                       |
### 🌀 Stream Ciphers
Stream ciphers encrypt data one bit or byte at a time, often used in real-time applications.
| Algorithm                  | Notes                             |
| -------------------------- | --------------------------------- |
| **RC4**                    | Deprecated due to vulnerabilities |
| **Salsa20** / **ChaCha20** | Modern and secure     

# 🐧 Linux-Based Tasks: Symmetric Key Cryptography
### ✅ Task 1: Use gpg for Symmetric Encryption
```bash
# Encrypt using gpg (will prompt for passphrase)
gpg -c secret.txt

# Decrypt
gpg secret.txt.gpg
```
### ✅ Task 2: Encrypt and Decrypt a File Using AES-256-CBC (with openssl)
```bash
# Create a test file
echo "This is a secret message" > filename.txt

# Encrypt the file using AES-256-CBC
openssl enc -aes-256-cbc -salt -in filename.txt -out filename.enc -k mypassword

# Decrypt the file
openssl enc -aes-256-cbc -d -in filename.enc -out decrypted.txt -k mypassword
```
### ✅ Task 3: Encrypt a Folder by Archiving + Encrypting
```bash 
# Create a test folder
mkdir foldername && echo "secret" > foldername/note.txt

# Archive and encrypt it
tar czf - foldername | openssl enc -aes-256-cbc -salt -out folder.tar.gz.enc -k mypassword

# Decrypt and extract
openssl enc -d -aes-256-cbc -in folder.tar.gz.enc -out folder.tar.gz -k mypassword
tar xzf folder.tar.gz
```
### ✅ Task 4: Experiment with Different AES Modes (ECB, CBC, CTR)
```bash
# AES-128-ECB
openssl enc -aes-128-ecb -in filename.txt -out out_ecb.enc -k mypassword

# AES-128-CBC
openssl enc -aes-128-cbc -in filename.txt -out out_cbc.enc -k mypassword

# AES-128-CTR
openssl enc -aes-128-ctr -in filename.txt -out out_ctr.enc -k mypassword
```
📌 Then decrypt each using the same command with -d.























