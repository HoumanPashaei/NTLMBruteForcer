# 🔐 NTLM Brute-Forcer with Multiprocessing and Auto-Redirect Detection

A powerful and customizable Python tool to brute-force NTLM-authenticated web services.  
Supports HTTP/HTTPS auto-detection, proxy usage, multiprocessing, and progress tracking.

## ⚙ Features

- ✅ NTLM Authentication via `requests-ntlm`
- 🚀 Multiprocessing for speed (uses all CPU cores by default)
- 🔁 Automatically detects and upgrades to HTTPS if redirected
- ↩️ Falls back to HTTP if HTTPS returns `401 Unauthorized`
- 🔍 Progress bar with real-time updates
- 🌐 Optional HTTP/SOCKS proxy support

## 📦 Requirements

- Python 3.7+
- [requests-ntlm](https://pypi.org/project/requests-ntlm/)

### Install dependencies:

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install requests requests-ntlm
```

---

## 🚀 Usage

```bash
python ntlm_brute.py -d <url> -u <username> -P <password_file>
```

### Arguments

| Argument       | Description                                         |
|----------------|-----------------------------------------------------|
| `-d`           | Target URL (can start with `http://` or `https://`) |
| `-u`           | Single username (e.g., `DOMAIN\\user`)             |
| `-U`           | File with list of usernames                        |
| `-P`           | File with passwords to try                         |
| `-x`           | Optional proxy URL (e.g. `http://127.0.0.1:8080`)  |
| `-w`           | Number of worker processes (default: CPU count)    |

---

### 🧪 Examples

Single username:
```bash
python ntlm_brute.py -d http://example.local/secure -u "CORP\\admin" -P passwords.txt
```

User list:
```bash
python ntlm_brute.py -d https://intranet.local/protected -U users.txt -P passwords.txt
```

Using a proxy:
```bash
python ntlm_brute.py -d http://target -u "DOMAIN\\user" -P pass.txt -x http://127.0.0.1:8080
```

---

## 🔒 Notes

- **Username Format:** Use `DOMAIN\\username` or `username@domain.local`
- **Target must support NTLM authentication** over HTTP or HTTPS
- If the target auto-redirects from HTTP → HTTPS, it will be handled automatically
- If the HTTPS response is 401, tool falls back to HTTP

---

## 📄 License

MIT License

---

## 👨‍💻 Author

Made with ❤️ by [Your Name or GitHub Handle]  
Feel free to contribute or open issues!
