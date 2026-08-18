# DarkMatter
Advanced Threat Intel tool and Threat Hunting Tool

[![Live Demo](https://img.shields.io/badge/LIVE_DEMO-Launch_DarkMatter-00f0ff?style=for-the-badge&logo=render&logoColor=black)](https://darkmatter-dashboard.onrender.com/)

![Status: Active](https://img.shields.io/badge/Status-Active_Deployment-00f0ff?style=for-the-badge)
![Role: Threat Hunting](https://img.shields.io/badge/Role-Threat_Hunting-8b5cf6?style=for-the-badge)
![Tech: Python & WebGL](https://img.shields.io/badge/Tech-Python_%7C_WebGL-black?style=for-the-badge)

# 🌌 DarkMatter // Threat Intel & Hunt Repository

**DarkMatter** is a proprietary, cinematic, browser-based command center engineered for advanced threat hunting and detection engineering. 

Built to replace sterile, spreadsheet-like security dashboards, DarkMatter utilizes a highly optimized WebGL/Three.js frontend and a lightweight Python proxy to aggregate threat intelligence, render 3D spatial infrastructure graphs, and synthesize complex SIEM detection queries in real-time.

---

## 🎯 Executive Overview

Modern SOC analysts and Threat Hunters lose critical response time pivoting between multiple intelligence platforms, sandboxes, and SIEMs. DarkMatter solves this by acting as a unified "Event Horizon." 

Analysts can drag-and-drop massive walls of obfuscated text or raw logs. The engine instantly shatters the data, extracts the IOCs, queries multiple intelligence APIs concurrently, and visualizes the adversary's infrastructure in a navigable 3D spatial graph—while automatically generating the exact KQL/Spotter syntax needed to hunt for the threat across the network.

---

## ⚡ Core Modules & Capabilities

### 1. The "Shatter" Parsing Engine
* **Drag-and-Drop Ingestion:** Drop raw text files, logs, or unstructured data directly into the browser. 
* **Auto-Extraction:** Automatically strips out and deduplicates IPs, Domains, and Hashes (MD5, SHA1, SHA256) using Regex, bypassing the need for manual formatting.
* **Auto-Defang:** Built-in toggles to safely defang/refang active URLs and IPs for safe sharing.

### 2. 3D Spatial Intelligence Graphing (WebGL)
* **Visual Correlation:** Every IOC generates an interactive 3D force graph detailing its physical location, associated malware families, open ports, and MITRE ATT&CK mappings.
* **Dynamic Threat States:** The UI autonomously reacts to the severity of the intelligence gathered:
  * **SYS.OP.NORMAL:** Standard blue/grey baseline for benign traffic.
  * **DEFCON 1 (Critical):** UI shifts to aggressive crimson when a highly malicious payload (5+ engine detections) is identified.
  * **DARK ENERGY (APT):** UI shifts to pulsating violet when infrastructure is definitively tied to a known Advanced Persistent Threat (APT) group.

### 3. "Hawking Radiation" (OSINT Leak Detection)
* Advanced adversaries often leave fragments of data behind. This module autonomously cross-references extracted IOCs against GitHub and ThreatFox.
* If leaked configurations, raw OSINT paste dumps, or malware analysis notes are detected, a **Radiation Leak** alert triggers, opening a side-panel with raw text snippets and direct links to the public dumps.

### 4. Detection Engineering & SIEM Synthesis
* Select anomalous nodes directly from the UI to instantly synthesize properly formatted, heavily optimized queries using `dynamic()` arrays and `IN()` operators.
* **Supported Platforms:**
  * Microsoft Defender (Advanced Hunting KQL)
  * Microsoft Sentinel (KQL)
  * Securonix Spotter
* *Integration Note:* Designed to act as the perfect intelligence precursor to feed internal bulk security query launchers and SOAR playbooks.

### 5. Persistent Threat Hunt Repository
* A dedicated, cloud-backed operations hub to save, categorize, and manage custom threat hunts (Network, Endpoint, Identity, Cloud).
* Stores the hunt objective, category, and all mapped SIEM queries for rapid redeployment by the SOC team.
* Features strict role-based access control (RBAC) via override passwords to prevent accidental deletion of critical operational playbooks.

---

## 📡 Intelligence Integrations

DarkMatter securely proxies API calls through the backend to bypass CORS restrictions and protect API keys, leveraging a 24-hour in-memory cache to preserve rate limits.

* **VirusTotal** (Engine Detections & Community Tags)
* **AlienVault OTX** (Pulse Tracking & Adversary Attribution)
* **ThreatFox** (Malware Family & Payload Mapping)
* **GreyNoise** (Mass-Scanner & RIOT Filtering)
* **AbuseIPDB** (Crowdsourced Confidence Scoring)
* **Shodan** (Exposed Ports & Services)
* **crt.sh** (Subdomain Certificate Parsing)
* **IP-API** (Geolocation, ASN, and Proxy/VPN/Datacenter tagging)

---

## 🔒 Architecture & Security Note

* **Backend:** Lightweight Python (`http.server`) acting as a secure API proxy and caching layer.
* **Frontend:** Vanilla JS, HTML5, CSS3, `Three.js`, `3d-force-graph`, `Globe.gl`.
* **Database:** Firebase Realtime Database (REST API integration) for ephemeral-safe hunt storage.
* **Zero-Logging:** The tool does not store queried IOCs, ensuring sensitive client telemetry and investigation targets remain strictly confidential and out of third-party logs.

> *"Security data doesn't have to be boring to be effective. Visualization is the key to velocity."*
