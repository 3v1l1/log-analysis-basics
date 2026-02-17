# Log Analysis Basics

This repository documents my beginner-level understanding of log analysis as part
of my journey toward a cybersecurity and SOC analyst role. The purpose of this
project is to show how a security analyst reads and interprets logs to identify
normal activity and potential security issues.

---

## What Are Logs?

Logs are records created by systems, applications, and network devices that
capture events happening over time. These events can include logins, errors,
connections, and system actions.

Logs help security analysts answer questions such as:
- What happened?
- When did it happen?
- Who or what was involved?

---

## Why Log Analysis Is Important in Cybersecurity

Log analysis allows analysts to:
- Detect suspicious or malicious activity
- Investigate security incidents
- Monitor system behavior
- Support incident response decisions

Most security incidents are discovered by reviewing logs rather than by direct
user reports.

---

## Common Types of Logs

### Authentication Logs
- Record login attempts and access events
- Useful for identifying brute-force attacks or unauthorized access

### System Logs
- Track system events such as startups, shutdowns, and errors
- Help identify abnormal system behavior

### Network Logs
- Capture network connections and traffic
- Useful for identifying suspicious communication patterns

---

## Example Log Entries (Simulated)

The following examples are fictional and used for learning purposes.

### Successful Login

2026-01-30 10:15:42 INFO User login successful
User: jdoe | IP: 192.168.1.10


### Failed Login Attempt

2026-01-30 10:18:03 WARN Failed login attempt
User: admin | IP: 203.0.113.45


### Repeated Failed Login Attempts

2026-01-30 10:18:10 WARN Failed login attempt
User: admin | IP: 203.0.113.45


---

## Analyst Notes on Successful Logins

A successful login event is usually normal behavior. However, a security analyst
still considers context before deciding whether the activity is safe.

An analyst may check:
- Whether the login came from a known or expected IP address
- Whether the login time matches normal user behavior
- Whether there were multiple failed attempts before the successful login
- Whether the account has elevated privileges

A successful login following repeated failures may indicate a compromised
account or brute-force attack.

---

## What Looks Suspicious in Logs?

Security analysts look for patterns rather than single events, such as:
- Multiple failed login attempts from the same IP
- Login attempts targeting privileged accounts
- Activity occurring outside normal working hours
- Access attempts from unfamiliar locations

---

## Basic Investigation Steps

When suspicious activity is identified, an analyst may:
1. Review related authentication and system logs
2. Identify the source IP address and user account
3. Check whether other systems were targeted
4. Determine if the activity matches known attack behavior
5. Decide whether escalation or response is required

---

## Basic Response Actions

Depending on the severity, response actions may include:
- Blocking or monitoring the suspicious IP address
- Resetting affected user credentials
- Notifying the security or IT team
- Increasing monitoring for similar activity

---

## Basic Linux Commands for Log Analysis

Security analysts often use Linux commands to review and filter logs.

- grep: Search for specific keywords inside logs
- cat: Display log file contents
- less: Scroll through large log files

Example:
grep "failed" auth.log

## Basic SQL Example for Log Review

Analysts may use SQL to search log data stored in databases.

Example query to identify failed login attempts:

SELECT * FROM logs
WHERE status = 'failed_login';


## Why This Matters for a SOC Analyst

Log analysis is a core responsibility of Security Operations Center (SOC)
analysts. Even at an entry level, analysts must understand how to read logs,
identify abnormal patterns, and respond appropriately.

This project demonstrates foundational log analysis and analyst thinking skills.

---

## Next Steps

- Continue developing SOC analyst skills
- Practice hands-on log review
- Learn how SIEM tools analyze logs
