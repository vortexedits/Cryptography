# 🔐 Asymmetric Key Cryptography
Unlike symmetric key cryptography, asymmetric cryptography uses a pair of keys:
- 🔑 Public Key: Can be shared with anyone.
  
-🔒 Private Key: Must be kept secret.

It is used for encryption, digital signatures, and secure key exchange.
### 🔢 Common Algorithms
| Algorithm          | Description                                                            |
| ------------------ | ---------------------------------------------------------------------- |
| **RSA**            | Uses modular exponentiation and large primes for encryption/signatures |
| **Diffie-Hellman** | Securely exchanges keys over an insecure channel                       |
| **ECC**            | Faster and smaller keys using elliptic curves                          |
| **ElGamal**        | Based on Diffie-Hellman; supports encryption and digital signatures    |
### ✉️ Key Concepts
| Concept          | Meaning                                       |
| ---------------- | --------------------------------------------- |
| **Public Key**   | Shared with others to encrypt or verify       |
| **Private Key**  | Kept secret; used to decrypt or sign          |
| **Key Exchange** | Technique to securely agree on shared secrets |
# 🔄 Summary of Key File Types
| File              | Description                 |
| ----------------- | --------------------------- |
| `private_key.pem` | RSA private key             |
| `public_key.pem`  | RSA public key              |
| `signature.bin`   | Digital signature           |
| `*.gpg`           | GPG encrypted file          |
| `pubkey.asc`      | Exported public key (ASCII) |
# 🐧 Linux-Based Tasks: Asymmetric Key Cryptography
### ✅ Task 1: Generate RSA Public and Private Keys Using openssl
```
# Generate a 2048-bit private key
openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048

# Extract the public key
openssl rsa -in private_key.pem -pubout -out public_key.pem
```
### ✅ Task 2: Encrypt and Decrypt a File Using RSA
RSA can only encrypt small files directly (e.g., up to 245 bytes with a 2048-bit key). For larger data, use hybrid encryption (encrypt AES key with RSA).
```
# Create a small file
echo "Confidential Data" > filename.txt

# Encrypt using public key
openssl rsautl -encrypt -inkey public_key.pem -pubin -in filename.txt -out encrypted.bin

# Decrypt using private key
openssl rsautl -decrypt -inkey private_key.pem -in encrypted.bin -out decrypted.txt

# View decrypted output
cat decrypted.txt
```
### ✅ Task 3: Generate and Verify Digital Signatures
# Sign a file using private key
```
openssl dgst -sha256 -sign private_key.pem -out signature.bin secret.txt

# Verify the signature using public key
openssl dgst -sha256 -verify public_key.pem -signature signature.bin secret.txt
```
 Output will be *Verified OK* if successful.
### ✅ Task 4: Use GPG for Asymmetric Encryption
🔑 Key Generation:
```
gpg --full-generate-key
```
🔍 View Keys:
```
gpg --list-keys
```
📦 Encrypt a File:
```
gpg -e -r "Your Name" file.txt
```
🔓 Decrypt the File:
```
gpg -d file.txt.gpg
```
### ✅ Task 5: Export and Import Public Keys with GPG
```
# Export
gpg --export -a "Your Name" > pubkey.asc

# Import (on another machine or user)
gpg --import pubkey.asc
```








