# Phishing Email Triage

**Ashique Meethale Purayil** · Simulated SOC case

## Scenario

An employee reported an email claiming to be from IT. It asked them to verify their account within 30 minutes. The approved staff portal in this exercise is `portal.example.org`.

## Evidence

| Check | Observation |
| --- | --- |
| From | The message claims to be from `helpdesk@example.org`. |
| Reply-To | Replies go to `support@example.net`, a different domain. |
| Sign-in link | The destination host is `account-check.example.net`, outside the approved portal domain. |
| Requested action | The message asks the employee to sign in before a short deadline. |

## Triage decision

**Suspected credential phishing.** Escalate the message for review. Sender authentication and whether the employee interacted with the link remain unverified.

## Recommended response

1. Preserve the reported message and its full headers. Verify the request through a known IT support channel.
2. Review sender authentication in the headers and search mail logs for other messages with the same link host.
3. If phishing is confirmed, quarantine matching messages. If the employee entered credentials, escalate for account recovery.
