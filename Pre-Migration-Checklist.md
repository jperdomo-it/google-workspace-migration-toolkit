# Technical Pre-Migration Checklist

This checklist ensures all technical requirements are met before moving any data to Google Workspace. Following these steps minimizes downtime and prevents mail delivery issues.

## 1. Domain & DNS Readiness
- [ ] **Verify Domain Ownership:** Ensure access to the DNS provider (GoDaddy, Cloudflare, Route53, etc.).
- [ ] **Lower TTL (Time To Live):** Reduce MX and SPF record TTL to 300 seconds (5 minutes) at least 24 hours before cutover.
- [ ] **Audit Existing Records:** Document current MX, TXT (SPF), and CNAME records to avoid breaking existing services (like web hosting or CRM).

## 2. Source Environment (Legacy System)
- [ ] **Mailbox Inventory:** Generate a list of all active users, aliases, and shared mailboxes.
- [ ] **Size Assessment:** Identify mailboxes exceeding 30GB (Google's standard limit for Business Starter).
- [ ] **Admin Credentials:** Ensure global admin access to the source (M365 Admin Center, Exchange, or IMAP server).
- [ ] **App Passwords/IMAP:** Enable IMAP and generate App Passwords if 2FA is active on the source.

## 3. Google Workspace Preparation
- [ ] **User Provisioning:** Create all user accounts matching the source naming convention.
- [ ] **Groups & Aliases:** Set up distribution lists (Groups) and email aliases.
- [ ] **Security Baseline:** - [ ] Enable 2-Step Verification (2FA) policy.
    - [ ] Configure DKIM (to prevent spoofing).
    - [ ] Prepare SPF record string: `v=spf1 include:_spf.google.com ~all`.

## 4. Migration Tools Setup
- [ ] **Authorization:** Grant API access to the migration tool (GWMME or Google Migration Service).
- [ ] **Connectivity Test:** Run a test migration for 1 "Pilot" user to verify credentials and speed.
- [ ] **Exclusion List:** Document any folders (like "Trash" or "Junk") that should be excluded from the sync.

---
*Note: This checklist is updated regularly based on Google Cloud's best practices.*
