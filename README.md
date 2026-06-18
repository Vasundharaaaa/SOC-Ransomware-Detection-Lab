# Security Operations Center (SOC) for Ransomware Detection

## Overview

This project demonstrates the design and implementation of a Security Operations Center (SOC) environment for centralized security monitoring, log analysis, and ransomware detection.

The solution integrates Wazuh, ELK Stack, Sysmon, and NXLog to collect, process, analyze, and visualize security events generated across multiple Windows endpoints. The environment provides real-time monitoring, file integrity monitoring, event correlation, and alert generation to support threat detection and incident response activities.

## Objectives

* Centralize security log collection from multiple endpoints.
* Detect ransomware-like behavior through custom monitoring rules.
* Monitor file integrity changes on critical files and directories.
* Correlate security events for faster threat analysis.
* Generate real-time alerts for suspicious activities.
* Simulate SOC operations within a controlled lab environment.

---

## Architecture

### High-Level Data Flow

1. Windows endpoints generate security events through Sysmon and native Windows Event Logs.
2. NXLog agents collect and forward logs from each endpoint.
3. Logs are simultaneously transmitted to:

   * Wazuh Manager for threat detection and security monitoring.
   * ELK Stack for centralized storage, search, and visualization.
4. Security analysts review events through:

   * Wazuh Dashboard
   * Kibana Dashboard

### Infrastructure Components

| Component         | Purpose                         |
| ----------------- | ------------------------------- |
| Windows Endpoints | Event generation and monitoring |
| Sysmon            | Advanced endpoint telemetry     |
| NXLog             | Log forwarding                  |
| Wazuh Manager     | Threat detection and alerting   |
| ELK Stack         | Log storage and analytics       |
| Wazuh Dashboard   | Security monitoring interface   |
| Kibana            | Visualization and analysis      |

---

## Features

### Security Monitoring

* Centralized log collection
* Endpoint security monitoring
* Security event analysis
* Event correlation

### Threat Detection

* Ransomware detection
* Suspicious process monitoring
* File modification detection
* Custom security rules

### File Integrity Monitoring

* Critical file monitoring
* Unauthorized modification detection
* Honey file monitoring
* Tamper detection

### Alerting

* Real-time alert generation
* Dashboard-based notifications
* Security incident visibility

---

## Technologies Used

### Security Monitoring

* Wazuh
* Sysmon
* NXLog

### Log Analytics

* Elasticsearch
* Logstash
* Kibana

### Operating Systems

* Ubuntu Linux
* Windows

### Security Concepts

* Security Operations Center (SOC)
* SIEM
* Log Management
* Threat Detection
* File Integrity Monitoring
* Incident Response
* Ransomware Detection

---

## Detection Workflow

1. Endpoint activity is monitored using Sysmon.
2. Security logs are collected by NXLog.
3. Logs are forwarded simultaneously to Wazuh and ELK.
4. Wazuh evaluates events against custom detection rules.
5. Suspicious activities generate security alerts.
6. Analysts investigate alerts through Wazuh Dashboard and Kibana.

---

## Security Use Cases

### Ransomware Detection

Detects ransomware-like behavior through file modification patterns and suspicious endpoint activities.

### File Integrity Monitoring

Monitors protected files and directories for unauthorized modifications.

### Threat Hunting

Supports manual investigation through centralized log search and event correlation.

### Incident Analysis

Provides historical log visibility and security event analysis capabilities.

---

## Learning Outcomes

Through this project, the following cybersecurity concepts were implemented and explored:

* Security Operations Center (SOC) Operations
* SIEM Deployment and Management
* Log Collection and Forwarding
* Threat Detection Engineering
* Event Correlation
* File Integrity Monitoring
* Endpoint Telemetry Analysis
* Incident Response Workflows
* Security Monitoring Automation

---

## Future Enhancements

* MITRE ATT&CK Mapping
* Advanced Detection Rules
* Threat Intelligence Integration
* Automated Incident Response
* Cloud-Based Log Collection
* Machine Learning-Based Anomaly Detection

---

## Author

**Vasuntthara Dhayalan**

B.E. Computer Science and Engineering (Cybersecurity)

Sri Krishna College of Technology (SKCT)


