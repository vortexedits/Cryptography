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
# 🐧 Linux-Based Hash Function Tasks
### ✅ Task 1: Hash a File Using md5sum, sha1sum, sha256sum 
```
# Create a test file
echo "mysecurepassword" > test.txt

# Generate MD5 hash
md5sum test.txt

# Generate SHA-1 hash
sha1sum test.txt

# Generate SHA-256 hash
sha256sum test.txt
```
### ✅ Task 2: Verify File Integrity Using a Checksum
```
# Save checksum
sha256sum test.txt > checksum.sha256

# Later: Verify
sha256sum -c checksum.sha256
```
### ✅ Task 3: Hash a Password Using openssl
```
echo -n "mypassword" | openssl dgst -sha256
echo -n "mypassword" | openssl dgst -md5
echo -n "mypassword" | openssl dgst -sha1
```
### ✅ Task 4: Detect File Tampering
Generate hash for an important file (e.g., /etc/passwd):
```
sha256sum /etc/passwd > passwd.sha256
```
Later, run: If output is FAILED, it means the file was modified.
```
sha256sum -c passwd.sha256
```





