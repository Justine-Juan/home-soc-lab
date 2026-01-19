## Summary

A new local user was created and added to the Administrators group, triggering alerts for privilege escalation.

## Alert Details

- Rule ID: 60154
- Source Host: WIN-ENDPOINT-01
- User Created: testuser_lab
- Timestamp: 2026-01-06 17:07
- Severity: High

![Privilege Escalation alert](screenshots/14-PrivilegeEscalationAlert.png)

## Investigation Steps

1. Filtered Wazuh Dashboard alerts by Rule ID 60154.
2. Reviewed Security Event Logs in Windows for account creation and group membership changes.
3. Verified user `testuser_lab` was added to Administrators.
4. Confirmed action timestamp matches lab activity.

## Findings

- The privilege escalation was performed intentionally for SOC lab testing.
- No unauthorized users or suspicious remote activity found.

## Verdict

Lab test — not malicious.

## Recommended Action

- Delete the test user from Administrators if desired.
- Document alert in SOC records for training purposes.
