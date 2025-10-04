# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information

<img width="1919" height="1079" alt="Screenshot 2025-10-04 090227" src="https://github.com/user-attachments/assets/531efa0e-bdff-42c6-a25f-4668fc7dcbce" />

<img width="1919" height="1015" alt="Screenshot 2025-10-04 090339" src="https://github.com/user-attachments/assets/05ac8485-5e68-41fb-b05b-cd8082534bbc" />

<img width="1914" height="1048" alt="Screenshot 2025-10-04 091020" src="https://github.com/user-attachments/assets/0be80216-3105-40c0-8ef2-2cdb6daeccf1" />

<img width="1919" height="1079" alt="Screenshot 2025-10-04 091153" src="https://github.com/user-attachments/assets/e4ce1e01-048a-4393-a6c7-ce5ed4b25af2" />

<img width="1919" height="1078" alt="Screenshot 2025-10-04 091208" src="https://github.com/user-attachments/assets/ab7349c9-e862-40af-a262-c8900857aa71" />

<img width="1917" height="1072" alt="Screenshot 2025-10-04 091235" src="https://github.com/user-attachments/assets/1205c4f3-36a4-4550-a4ca-873eeed26a76" />

<img width="1919" height="912" alt="Screenshot 2025-10-04 091809" src="https://github.com/user-attachments/assets/980cae94-1697-4eeb-af40-dc73d931c0f2" />

<img width="1919" height="975" alt="Screenshot 2025-10-04 091834" src="https://github.com/user-attachments/assets/74ac3615-7211-4e81-a380-11f8d14921f9" />

<img width="1919" height="700" alt="Screenshot 2025-10-04 091846" src="https://github.com/user-attachments/assets/59efdd20-a5e9-4afc-9826-4dec67a3a4aa" />

<img width="1919" height="950" alt="Screenshot 2025-10-04 091856" src="https://github.com/user-attachments/assets/26182f18-9ad1-486e-bc08-9b9d429af37c" />


## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

