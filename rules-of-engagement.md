# Personal Rules of Engagement (ROE) — Isolated Security Practice Lab

**Version:** 1.0  
**Purpose:** Establish safe, legal, reproducible conditions for security testing.

## 1. Authorization
I authorize testing only against the local OWASP Juice Shop instance that I start and control on my own computer, at `http://127.0.0.1:3000`. This document does not grant permission to test any other system.

## 2. Target and scope
**In scope**
- The local Juice Shop web application in this lab.
- Manual browsing and normal interaction with its training challenges.
- Reading browser developer-tools output and response headers for the local target.
- Low-rate, non-destructive validation directed only to `127.0.0.1:3000`.
- Recording observations and screenshots that contain no secrets or personal data.

**Out of scope**
- Any public website, internet-facing IP, school/college or employer system, shared network, other person's device/account, or system not explicitly owned or controlled by me with written authorization.
- The Docker host operating system, other containers, router, Wi-Fi/LAN devices, cloud services, and third-party APIs.
- Denial-of-service, load/stress testing, destructive actions, persistence, malware, credential theft, phishing, social engineering, or attempts to access real users' data.
- Scanning beyond the local target, evading monitoring, or testing if the target identity is uncertain.

## 3. Isolation requirements
- Bind the service only to `127.0.0.1:3000`, never `0.0.0.0`.
- Use the Docker network configured with `internal: true`.
- Do not use router port forwarding, public tunnels, or remote access.
- Use fictional test data only; never enter real credentials or personal information.
- Keep testing low-rate and limited to the stated target.

## 4. Permitted techniques
- Manual browsing and application feature exploration.
- Reviewing response headers and browser developer-tools output.
- Completing intentionally provided Juice Shop training challenges.
- Non-destructive, low-volume checks of the local target that do not violate the exclusions above.

## 5. Stop conditions
Stop immediately if:
- The destination is not exactly the local lab target or the scope is uncertain.
- The service becomes unstable, the host behaves unexpectedly, or another system may be affected.
- Real personal data, credentials, or secrets appear.
- An action could be destructive, disruptive, or exceed the permitted techniques.
- I lose control of the computer or cannot confirm the network boundary.

After stopping, record the issue and shut down the lab if needed. Do not resume until the scope and safety issue are understood.

## 6. Evidence and reporting
For each activity, record date/time, target, action, expected result, observed result, and cleanup. Store screenshots and logs in this project folder. Redact secrets and personal information before sharing.

## 7. Personal confirmation
I have read these rules and agree to follow them. I understand that I must not test systems I do not own or control, and that this document does not authorize testing any third-party system.

**Full name:** __________________________________________

**Signature:** ___________________________________________

**Date (YYYY-MM-DD):** _________________________________

**Authorized lab target:** `http://127.0.0.1:3000`
