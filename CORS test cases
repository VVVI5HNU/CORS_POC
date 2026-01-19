## 🔍 Testing for CORS Misconfigurations

This section outlines **common manual testing techniques** used to identify **CORS (Cross-Origin Resource Sharing) misconfigurations** during Web Application Security Testing (VAPT).

---

## 🧪 CORS Testing Methodology

When testing an endpoint for CORS issues, focus on **manipulating the `Origin` header** and observing the server’s response headers.

---

### 1️⃣ Arbitrary Origin Value

Change the `Origin` header to an attacker-controlled domain:

```http
Origin: https://attacker.com
```

✅ Vulnerable if:
- `Access-Control-Allow-Origin` reflects the arbitrary origin
- Credentials are allowed

---

### 2️⃣ Null Origin Test

Set the `Origin` header to `null`:

```http
Origin: null
```

✅ Vulnerable if:
- Server responds with:
  ```
  Access-Control-Allow-Origin: null
  ```
- Especially dangerous when credentials are enabled

---

### 3️⃣ Origin Prefix Matching

Change the origin to one that **begins with the legitimate domain**:

```http
Origin: https://target.com.attacker.com
```

✅ Vulnerable if:
- Server performs weak prefix matching
- Origin is accepted without strict validation

---

### 4️⃣ Origin Suffix Matching

Change the origin to one that **ends with the legitimate domain**:

```http
Origin: https://attacker-target.com
```

✅ Vulnerable if:
- Server uses suffix-based matching
- Origin validation relies on `endsWith` logic

---

## 🔍 What to Look For in the Response

Check the following response headers:

```http
Access-Control-Allow-Origin
Access-Control-Allow-Credentials
```

🚨 High risk if:
- Arbitrary origins are reflected
- `Access-Control-Allow-Credentials: true` is present
- Sensitive endpoints return authenticated data

---

## 💥 Impact

Successful exploitation of CORS misconfigurations may lead to:
- Leakage of sensitive user data
- Session hijacking
- Account takeover
- Unauthorized API access

---

## 🛡 Mitigation

- Use a strict allowlist for trusted origins
- Avoid wildcard origins when credentials are enabled
- Never reflect user-controlled origins blindly
- Validate origins on the server side
- Disable credentials unless strictly required

---

## 📚 References

- OWASP: Cross-Origin Resource Sharing (CORS)
- PortSwigger Web Security Academy – CORS
- CWE-942: Permissive Cross-domain Policy

---

## ✅ End of Section
