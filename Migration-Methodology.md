# Google Workspace Migration Methodology

This document outlines my professional approach to migrating business data from legacy systems (M365, Exchange, IMAP) to Google Workspace.

## 1. Discovery & Planning
* **Infrastructure Audit:** Reviewing current mail flow, storage volume, and user count.
* **DNS Assessment:** Checking current TTL, SPF, and MX records.
* **Gap Analysis:** Identifying features in the source system that need specific mapping in Google Workspace.

## 2. Pre-Migration Setup
* **Provisioning:** Creating users and Groups via CSV or GAM.
* **Security Baseline:** Configuring 2FA, DKIM, and DMARC before the first email is sent.
* **Routing:** Setting up dual delivery or split delivery if required.

## 3. Execution (The Migration)
* **Phased Approach:** Running a pilot migration with "power users" first.
* **Delta Migrations:** Ensuring the most recent data is synced right before the cutover.

## 4. Post-Migration & Support
* **Offboarding:** Safely decommissioning the old server.
* **Training:** Providing "Go-Live" guides for end-users.
