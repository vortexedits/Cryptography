# 🔐 Introduction to Cryptography
Cryptography is the science of securing communication in the presence of adversaries.

It plays a vital role in information security, ensuring:
- Confidentiality
- Integrity
- Authentication
- Non-repudiation
# 🧠 Types of Cryptography
| Type              | Description                                 |
| ----------------- | ------------------------------------------- |
| 🔑 Symmetric-Key  | Same key for encryption and decryption.     |
| 🔓 Asymmetric-Key | Uses Public & Private key pairs.            |
| 🔁 Hash Functions | One-way, irreversible, fixed-length output. |
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
| **Salsa20** / **ChaCha20** | Modern and secure                 |
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
# 🧮 Hash Functions
A hash function is a one-way function that maps input data of any length into a fixed-size string of bytes — typically a digest that uniquely identifies the input.
### 🧱 Properties of Cryptographic Hash Functions
| Property                        | Description                                                      |
| ------------------------------- | ---------------------------------------------------------------- |
| **Deterministic**               | Same input always gives same output                              |
| **Pre-image Resistance**        | Hard to reverse a hash to find the original input                |
| **Second Pre-image Resistance** | Hard to find different input with the same hash as a given input |
| **Collision Resistance**        | Hard to find two different inputs with the same hash             |
### 🔁 Popular Hash Algorithms
| Algorithm | Status   | Description                            |
| --------- | -------- | -------------------------------------- |
| **MD5**   | ❌ Broken | Produces 128-bit hash; easy to collide |
| **SHA-1** | ❌ Broken | 160-bit; not collision-resistant       |
| **SHA-2** | ✅ Secure | Includes SHA-256, SHA-512              |
| **SHA-3** | ✅ Secure | Keccak-based; NIST-approved successor  |


