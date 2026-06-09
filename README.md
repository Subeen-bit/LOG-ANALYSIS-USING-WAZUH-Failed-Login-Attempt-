# LOG-ANALYSIS-USING-WAZUH-Failed-Login-Attempt-

### Log Analysis

Log analysis is the process of examining system-generated logs to identify suspicious activities, security threats, and system behaviour. 

## Objective

In this project, logs collected from the monitored Kali Linux system and it is analysed using the Wazuh dashboard.
The Wazuh agent collects logs from the endpoint and forwards them to the Wazuh manager, where they are processed, indexed, and analysed in the dashboard for analysis.

### LOG COLLECTION MECHANISM

The Wazuh agent installed on Kali Linux continuously monitors system log files such as:

- /var/log/auth.log (authentication logs)
- syslog (system logs)

These logs are forwarded in real time to the Wazuh manager. The wazuh manager analyses the logs using predefined rules and generates alerts based on suspicious patterns.

## FAILED LOGIN ATTEMPT DETECTION

Procedure:

https://github.com/Subeen-bit/LOG-ANALYSIS-USING-WAZUH-Failed-Login-Attempt-/blob/main/Screenshot%202026-04-27%20233255.png

`su root`

A failed login attempt was simulated using the command sudo su and incorrect password was entered will generate authentication failures.

Log generation:

Detection in Wazuh:
The Wazuh dashboard detected these events and displayed alerts with details such as:

- Description: PAM: User login failed
- Rule ID: 5503
- Severity Level: 5

### Conclusion

Analysis:

Failed login attempts indicate potential unauthorized access attempts. Multiple repeated failures can suggest brute-force attack behaviour.
