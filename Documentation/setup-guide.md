# Setup Guide

## Overview

This document describes the deployment and configuration process for the Security Operations Center (SOC) for Ransomware Detection environment.

The lab was designed to centralize security monitoring, collect endpoint telemetry, and detect ransomware-related activities using Wazuh, ELK Stack, Sysmon, and NXLog.

---

# Lab Components

| Component         | Purpose                          |
| ----------------- | -------------------------------- |
| Windows Endpoints | Event generation and monitoring  |
| Sysmon            | Advanced endpoint telemetry      |
| NXLog             | Log forwarding                   |
| Wazuh Manager     | Security monitoring and alerting |
| ELK Stack         | Log storage and analytics        |
| Wazuh Dashboard   | Security monitoring interface    |
| Kibana            | Log visualization                |

---

# Environment Setup

## Wazuh Server

Operating System:

* Ubuntu Linux

Installed Components:

* Wazuh Manager
* Wazuh Indexer
* Wazuh Dashboard
* Filebeat

Responsibilities:

* Agent management
* Security rule evaluation
* Alert generation
* File Integrity Monitoring (FIM)

---

## ELK Stack Server

Installed Components:

* Elasticsearch
* Logstash
* Kibana

Responsibilities:

* Log ingestion
* Log storage
* Event correlation
* Dashboard visualization

---

## Windows Endpoints

Installed Components:

* Sysmon
* NXLog Agent

Responsibilities:

* Event generation
* Endpoint telemetry collection
* Log forwarding

---

# Sysmon Configuration

Sysmon was deployed on Windows endpoints to capture detailed security events including:

* Process creation
* Network connections
* File creation
* Registry modifications
* Driver loading
* Image loading events

Configuration file:

```text
Configurations/sysmonconfig.xml
```

---

# NXLog Configuration

NXLog was configured to:

* Collect Windows Event Logs
* Forward Sysmon events
* Send logs to Wazuh Manager
* Send logs to ELK Stack

Configuration file:

```text
Configurations/nxlog.conf
```

---

# Wazuh Configuration

Wazuh Manager was configured to:

* Receive endpoint logs
* Process security events
* Generate alerts
* Monitor file integrity
* Evaluate custom detection rules

Configuration file:

```text
Configurations/ossec.conf
```

---

# Detection Rules

Custom rules were developed to identify:

* Ransomware-like activity
* Unauthorized file modifications
* Suspicious endpoint behavior
* Security monitoring events

Rules file:

```text
Detection-Rules/custom-rules.xml
```

---

# File Integrity Monitoring

Wazuh File Integrity Monitoring (FIM) was enabled to monitor:

* Critical directories
* Honey files
* Protected assets

Alerts were generated when monitored files were:

* Created
* Modified
* Deleted
* Renamed

---

# Detection Workflow

1. Endpoint activity occurs.
2. Sysmon generates telemetry.
3. NXLog collects security events.
4. Logs are forwarded simultaneously to Wazuh and ELK.
5. Wazuh evaluates events against custom rules.
6. Alerts are generated for suspicious activities.
7. Analysts investigate events using Wazuh Dashboard and Kibana.

---

# Validation

The environment was validated through controlled simulations involving:

* File modification events
* Honey file access
* File integrity violations
* Ransomware-like behaviors

Detection results were successfully observed through:

* Wazuh Dashboard
* Kibana Dashboard
* Alert generation workflows

---

# Repository Structure

Refer to the project README for architecture diagrams, screenshots, and project overview information.
