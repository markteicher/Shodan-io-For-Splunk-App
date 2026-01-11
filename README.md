# Shodan.io for Splunk App

## Overview

Shodan.io for Splunk provides direct visibility into **internet-facing infrastructure exposure** using the Shodan REST APIs.

This Splunk App enables security teams to **discover, monitor, analyze, and operationalize external exposure intelligence** directly in Splunk—without relying on the Shodan.io web interface.

The app is designed for **engineering-grade accuracy, auditability, and scale**, turning raw Shodan telemetry into actionable Splunk data.

---

## Supported Intelligence Types

Shodan provides visibility into the following external-facing asset and exposure classes:

- IP Addresses
- Open Ports and Services
- Service Banners
- Software and Product Fingerprints
- SSL/TLS Certificates
- Known Vulnerabilities (CVEs)
- Autonomous System Numbers (ASNs)
- Organizations
- Hostnames and Reverse DNS
- Geolocation Metadata
- Internet-wide Search Results

---

## Features

### 🛡️ Core Capabilities

| Feature | Description |
|------|-------------|
| 🌐 External Asset Visibility | Identify exposed hosts and services |
| 🔍 Internet-Wide Search | Query Shodan’s global index |
| 🧭 Host Intelligence | Deep per-IP service inspection |
| 🧬 Exposure Context | Ports, banners, software, and protocols |
| 🕵️ Vulnerability Signals | Observed CVE references |
| 🧾 Evidence Preservation | Raw API responses retained |

---

### 📈 Analytics and Visibility

| Feature | Description |
|------|-------------|
| 📊 Exposure Trends | Track changes in exposed services |
| 🔄 First-Seen Detection | Identify newly observed assets |
| 🧱 Infrastructure Mapping | IP → ASN → Organization context |
| 🔐 TLS Visibility | Certificate inventory and metadata |
| 🧠 Investigative Pivoting | Pivot across IPs, services, and CVEs |

---

### ⚙️ Operational Excellence

| Feature | Description |
|------|-------------|
| 📡 Modular Input Framework | Secure API-based ingestion |
| 🔑 Credential Management | Encrypted API key storage |
| 🌐 Proxy Support | Enterprise proxy compatibility |
| 🩺 Health Monitoring | API reachability and status |
| 📋 Operational Logging | Full ingestion traceability |
| ⏱️ Rate-Limit Awareness | Safe throttling and retries |

---

## 📊 Dashboards

| Dashboard | Description |
|---------|-------------|
| Overview | High-level exposure summary |
| Internet Exposure | Open ports and services |
| Vulnerabilities | Observed CVE signals |
| New Assets | Newly observed hosts |
| Certificates | TLS and certificate metadata |
| ASN Exposure | ASN-level exposure analysis |
| Search Analytics | Search query trends |
| Operations | Ingestion status and metrics |
| Health | API and data freshness monitoring |

Dashboards prioritize **clarity, traceability, and investigative workflows**.

---

## 🧾 Sourcetypes

The app ingests raw JSON events using the following sourcetypes (as configured in default inputs):

### Host Intelligence
- shodan:host
- shodan:service
- shodan:certificate

### Search and Discovery
- shodan:search_result
- shodan:query_result

### Vulnerability Signals
- shodan:vulnerability

### DNS and Attribution
- shodan:dns
- shodan:asn
- shodan:organization

### Operational Telemetry
- shodan:collector_status
- shodan:collector_error

---

## 🧭 Navigation Structure

Navigation matches default data UI configuration:

### Overview
- Overview

### Dashboards
- Internet Exposure
- Vulnerabilities
- Certificates
- ASN Exposure
- Search Analytics
- New Assets
- Operations
- Health

### Manage
- Hosts
- Services
- Vulnerabilities
- Certificates
- Search Queries
- Watchlists

### Platform
- Inputs
- API Status
- Operational Logs

### Help
- Support and Troubleshooting

---

## Deployment

### Step 1: Install the App

1. Download Shodan_For_Splunk_App-1.0.0.tar.gz
2. In Splunk Web, go to Apps → Manage Apps
3. Select Install app from file
4. Upload the package
5. Restart Splunk if prompted

---

### Step 2: Configure the App

This app uses a guided setup workflow to ensure secure and compliant configuration.

Navigate to Apps → Shodan.io for Splunk → Setup to configure:

- Shodan API key (stored securely)
- Optional enterprise proxy settings
- Modular input enablement and polling intervals

All inputs are disabled by default and must be explicitly enabled.

#### API Configuration
- Shodan API Key
- API Base URL  
  https://api.shodan.io
- Request Timeout
- Verify SSL Certificates

#### Proxy Configuration (Optional)
- Enable Proxy
- Proxy URL
- Proxy Username
- Proxy Password

#### Data Inputs
- Host Lookups
- Search Queries
- IP Watchlists
- Domain Monitoring
- ASN Monitoring

---

### Step 3: Validate Configuration

- Test API connectivity
- Validate authentication
- Verify API plan limits
- Automatic validation on first launch

---

### Step 4: Verify Data Collection

Run the following search in Splunk:

    index=security_shodan sourcetype=shodan:*
    | stats count by sourcetype

---

## 📦 Requirements

- Splunk Enterprise or Splunk Cloud
- Python 3.x (Splunk bundled)
- Shodan API Access (paid plans recommended)
- Network access to api.shodan.io

---

## ✅ AppInspect Compliance

- Proper Splunk directory structure
- No hardcoded credentials
- Inputs disabled by default
- Encrypted credential storage
- app.manifest included
- Apache License
- Setup-based configuration

---

## 🛠️ Troubleshooting

### No Data Appearing
- Verify API key permissions
- Confirm inputs are enabled
- Check API usage limits
- Review Splunk internal logs

### API Errors
- Validate API plan capabilities
- Confirm rate limits
- Check Shodan service status

### Proxy Issues
- Validate proxy connectivity
- Confirm SSL inspection compatibility
- Test proxy reachability from Splunk

---

## 📚 References

- Shodan REST API  
  https://developer.shodan.io/api

- Shodan Documentation  
  https://docs.shodan.io

- Splunk Documentation  
  https://docs.splunk.com

---

## 📜 License

Apache License
