## Summary

A new Windows service was created, triggering a high-level alert for potential persistence techniques.

## Alert Details

- Event ID: 7045
- Source Host: WIN-ENDPOINT-01
- Process: TestService
- Timestamp: 2026-01-06 17:01
- Severity: High

![Service creation alert](screenshots/11-ProcessCreationAlert.png)

## Investigation Steps

1. Filtered Wazuh Dashboard for Event ID 7045.
2. Checked the newly created service in `services.msc`.
3. Verified the service path: `cmd.exe /c echo SOC-Test`.
4. Confirmed creation timestamp aligns with lab test execution.

## Findings

- Service was created as part of SOC lab exercises.
- No malicious payload or unexpected processes detected.

## Verdict

Lab test — not malicious.

## Recommended Action

- Delete the test service using `sc delete TestService`.
- Record in SOC lab documentation for alert validation.
