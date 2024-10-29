

# 🌐 Website Status Checker

A Python tool to read a list of website URLs from a CSV file, check each URL’s HTTP status, and print a user-friendly description for each site (e.g., "200 OK" for accessible sites or "404 Not Found" for missing pages). Perfect for monitoring uptime or verifying a list of URLs!

---

## 📋 Features

- **CSV URL Input**: Reads URLs from a CSV file, ensuring quick setup.
- **HTTPS Enforcement**: Automatically formats each URL to start with `https://` for secure access.
- **Browser-Like Requests**: Uses a random User-Agent to make requests look like they’re coming from a real browser.
- **Clear Status Descriptions**: Converts numeric HTTP codes (e.g., `404`) into descriptive messages (e.g., "404 Not Found").
- **Error Handling**: Reports any issues if a website can’t be reached or has an unknown status.

---

## 🚀 Getting Started

### 🛠 Prerequisites

- **Python 3.x** installed on your machine.
- Install the required packages using:
  ```bash
  pip install requests fake-useragent
  ```

---

### 📂 Project Structure

```plaintext
.
├── README.md                  # Project documentation
├── websites.csv               # Input CSV file with website URLs (see format below)
└── website_status_checker.py  # Main Python script for the program
```

### 📥 Input CSV Example (`websites.csv`)

Make sure your CSV file is structured as follows:
| ID  | URL                     |
|-----|-------------------------|
| 1   | "netflix.com"           |
| 2   | "forbidden.com"         |
| 3   | "apple.com"             |
| 4   | "example.com/404"       |
| 5   | "microsoft.com"         |
| 6   | "nonexistentwebsitexyz123.com" |
| 7   | "amazon.com"            |
| 8   | "spotify.com"           |
| 9   | "tradingview.com"       |
| 10  | "udemy.com"             |

---

## 📝 Usage

1. **Clone the repository** (or download the `website_status_checker.py` and `websites.csv` files).
2. **Run the program** with:
   ```bash
   python website_status_checker.py
   ```
3. **Check the output** in your terminal. Each URL’s status will be printed with a readable description.

---

## 💻 Code Explanation

### Main Components:

- **`get_websites`**: Reads and formats URLs from `websites.csv`.
- **`get_user_agent`**: Generates a random User-Agent string.
- **`check_website`**: Checks each URL’s status and prints the result.
- **`main`**: Coordinates the program flow, calling each function in sequence.

### Sample Output
```plaintext
https://netflix.com (200 OK) Request fulfilled, document follows
https://forbidden.com (403 FORBIDDEN) Server understands, but refuses to authorize
https://apple.com (200 OK) Request fulfilled, document follows
https://example.com/404 (404 NOT FOUND) Resource not found
https://microsoft.com (200 OK) Request fulfilled, document follows
https://nonexistentwebsitexyz123.com (404 NOT FOUND) Resource not found
https://amazon.com (200 OK) Request fulfilled, document follows
https://spotify.com (200 OK) Request fulfilled, document follows
https://tradingview.com (200 OK) Request fulfilled, document follows
https://udemy.com (200 OK) Request fulfilled, document follows
```

---

## ⚙️ How It Works

1. **Load URLs** from the `websites.csv` file.
2. **Add HTTPS** if it’s missing from each URL.
3. **Simulate a Browser Request** using a User-Agent.
4. **Check HTTP Status** of each website, printing a readable message for each.

