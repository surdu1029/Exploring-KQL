# Exploring-KQL (Sanitized Pack)

This folder contains KQL queries extracted from the provided PDF and sanitized to remove environment-specific identifiers.

## Placeholders you must replace
- `<URL>`
- `<DEVICE_NAME>`
- `<ADMIN_ACCOUNT_OR_PATTERN>`
- `<SOC_MAILBOX_UPN>`
- `<TENANT_ID>`
- `<EXCLUDED_SHAREPOINT_DOMAIN>`
- `<IDENTIFIER>`

## Files
- `kql/officeactivity/who_clicked_officeactivity.kql` — Track who clicked a specific URL via OfficeActivity
- `kql/network/who_got_admin_account_commonsecuritylog.kql` — Find events involving a specific admin account in CommonSecurityLog
- `kql/endpoint/usb_file_copy_deviceevents_devicefileevents.kql` — Correlate USB drive mount + file creation on that drive
- `kql/identity/lockout_wrongpassword_identitylogonevents.kql` — Summarize WrongPassword/UnknownUser failures for a target identifier
- `kql/cloud/sharepoint_domains_used_cloudappevents.kql` — List SharePoint origin domains seen in CloudAppEvents
- `kql/email/phishing_networkmessageid_correlation.kql` — Correlate triage subject → NetworkMessageId and enrich with attachments/URLs/auth details
- `kql/endpoint/asr_rule_events_deviceevents.kql` — List ASR rule events for a device
- `kql/hunting/sensitive_password_files_union.kql` — Consolidated hunt for password/credential file indicators

## Safety
Before pushing, run a secret scan (e.g., gitleaks/trufflehog) and verify no tenant IDs, real domains, user UPNs, IPs, or hostnames are present.
