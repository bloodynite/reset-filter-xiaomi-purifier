# Xiaomi Air Purifier -- Filter Reset Command Generator

🔥 **Live Tool:**\
👉 **https://bloodynite.github.io/reset-filter-xiaomi-purifier**
*(Free, no login required, runs entirely in your browser)*
------------------------------------------------------------------------

## 🌟 What Is This?

A simple web tool that generates the **filter reset command** used by
various Xiaomi Air Purifier models:

-   Mi Air Purifier 3H\
-   Mi Air Purifier Pro / Pro H\
-   Xiaomi Air Purifier 4 / 4 Pro\
-   And other models using the same local protocol

The command is calculated from the device's serial number (UUID) using
SHA‑1 hashing and specific index extraction.

------------------------------------------------------------------------

## 🚀 Features

### ✔ Automatic Serial Formatting

-   Accepts raw or colon‑separated input.
-   Automatically formats it into: `XX:XX:XX:XX:XX:XX:XX`
-   Invalid characters are cleaned as you type.

### ✔ Command Generation Logic

The tool: 1. Cleans and parses the UUID into bytes.\
2. Computes a SHA‑1 hash.\
3. Uses the first hash byte to calculate four indexes:\
- `i0 = b0 % 20`\
- `i1 = (b0 + 5) % 20`\
- `i2 = (b0 + 13) % 20`\
- `i3 = (b0 + 17) % 20` 4. Extracts 4 bytes from the SHA‑1 hash at those
positions.\
5. Builds the final reset command:

    1B <byte1><byte2><byte3><byte4>,3008,A20800000000

### ✔ One‑Click Copy

Instantly copy the generated command to your clipboard.

### ✔ Debug Panel (Optional)

Shows: - Cleaned serial number\
- SHA‑1 hash\
- Extracted bytes\
- Calculated indices\
- Final command

Perfect for validation and technical analysis.

### ✔ Quick Reset

A simple **Reset** button clears all fields and hides results.

------------------------------------------------------------------------

## 🌐 Official Live Site

🟢 **Try it here:**\
\### 👉 https://bloodynite.github.io/reset-filter-xiaomi-purifier/

The page: - Works fully offline\
- Sends *no data* to any server\
- Is open source\
- Loads instantly thanks to GitHub Pages

------------------------------------------------------------------------

## 📦 How to Use

1.  Open the site.\
2.  Enter or paste your purifier's UUID.\
3.  Click **Generate**.\
4.  Copy the command and use it with your preferred tool or integration.

------------------------------------------------------------------------

## 🧠 Why This Exists

For advanced users who want to: - Control their purifier without Mi
Home\
- Automate local commands\
- Integrate with Home Assistant, MQTT, or custom scripts\
- Understand Xiaomi's local protocol behavior

------------------------------------------------------------------------

## 🛠 Technologies Used

-   HTML + CSS\
-   Vanilla JavaScript\
-   CryptoJS\
-   GitHub Pages

------------------------------------------------------------------------

## 📄 License

MIT License --- free for personal and commercial use.

------------------------------------------------------------------------

## 🤝 Contributions

Pull requests, improvements, and bug reports are welcome!
