# Xiaomi Air Purifier – Filter Reset Command Generator

SITE ['https://bloodynite.github.io/reset-filter-xiaomi-purifier/']

A simple web-based tool that generates the **filter-reset command** required by many Xiaomi Air Purifier models (3H, Pro, 4 Pro, Mi Pro H, and others).  
The tool converts the device serial number (UUID) into a SHA-1–based command sequence used by the purifier’s internal protocol.

---

## 🌟 Features

### ✔ Automatic Serial Formatting
- Accepts raw or formatted hex serial numbers.
- Automatically formats the input to:  
  `XX:XX:XX:XX:XX:XX:XX`
- Rejects invalid characters and normalizes pasted text.

### ✔ Command Generation
Given a serial number, the tool:
1. Cleans and parses the hex string.
2. Computes a SHA-1 hash of the serial bytes.
3. Uses the first hash byte to calculate four indices:
   - `i0 = b0 % 20`  
   - `i1 = (b0 + 5) % 20`  
   - `i2 = (b0 + 13) % 20`  
   - `i3 = (b0 + 17) % 20`
4. Extracts the corresponding bytes from the SHA-1 result.
5. Builds the final reset command
