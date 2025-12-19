# CORS_POC
Proof of Concept demonstrating Cross-Origin Resource Sharing (CORS) misconfigurations and their security impact for educational and authorized security testing.
# CORS Misconfiguration Proof of Concept (PoC)

> ⚠️ **Disclaimer**  
> This repository is intended strictly for **educational, defensive, and authorized security testing purposes**.  
> Test only applications that you own or have explicit permission to assess.  
> The author is not responsible for misuse of this information.

---

## 📌 Overview

This repository contains a **Proof of Concept (PoC)** to demonstrate **Cross-Origin Resource Sharing (CORS) misconfigurations** in web applications.

CORS misconfigurations can allow attackers to:
- Read sensitive responses from another origin
- Abuse overly permissive CORS policies
- Perform unauthorized cross-origin data access

This PoC helps security testers and developers **understand, identify, and validate** common CORS issues.

---

## 🧠 What is CORS?

Cross-Origin Resource Sharing (CORS) is a browser security mechanism that controls how web applications share resources across different origins.

Incorrect or overly permissive CORS configurations can expose sensitive data to malicious websites.

---

## 🔍 Common CORS Misconfigurations

This PoC focuses on identifying scenarios such as:

- `Access-Control-Allow-Origin: *` with credentials enabled
- Reflecting attacker-controlled `Origin` header
- Trusting arbitrary subdomains
- Missing or weak validation of allowed origins
- Insecure handling of `Access-Control-Allow-Credentials`

---

## 🧪 Proof of Concept

The provided script demonstrates how a misconfigured CORS policy can be abused to access protected responses from a different origin.

### Typical PoC Flow
1. A crafted request is sent with a malicious `Origin` header
2. The server responds with permissive CORS headers
3. The browser allows cross-origin access to the response
4. Sensitive data becomes accessible to the attacker-controlled origin

> The exact exploitation logic is implemented in the provided script file.

---

## ▶️ Usage

1. Download or clone this repository
2. Review the PoC script to understand the logic
3. Run the script against an **authorized target** following the script’s instructions

> Refer to comments inside the script for execution details.

---

## 📤 Expected Results

- **If vulnerable:**  
  The response will include permissive CORS headers allowing cross-origin access.

- **If not vulnerable:**  
  The browser or server will block the cross-origin request.

---

## 💥 Impact

Successful exploitation of a CORS misconfiguration may lead to:

- Sensitive data exposure
- Account information leakage
- Unauthorized API access
- Abuse of authenticated sessions (in some scenarios)

---

## 🛡 Mitigation & Best Practices

- Explicitly whitelist trusted origins
- Avoid using wildcard origins with credentials
- Validate the `Origin` header strictly
- Do not reflect arbitrary origins
- Apply least-privilege CORS policies

---

## 📚 References

- OWASP: Cross-Origin Resource Sharing (CORS)  
  https://owasp.org/www-community/attacks/CORS_OriginHeaderScrutiny
- OWASP Top 10
- CWE-942: Permissive Cross-domain Policy

---

## 📜 License

MIT License

---

## ✅ End of README
