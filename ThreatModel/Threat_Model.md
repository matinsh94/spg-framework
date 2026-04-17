Secure Policy Gateway (SPG) - Threat Model

1. Threat Overview
SPG is designed to mitigate threats associated with session-based trust systems by enforcing operation-level authentication.

2. Threat Actors
- External attackers (unauthorized access attempts)
- Malicious insiders (abuse of valid sessions)
- Compromised devices (physical or remote access)
- Automated attack tools (replay / brute force attempts)

3. Identified Threats

3.1 Session Hijacking
Attackers may gain control of an active authenticated session.

Mitigation:
SPG enforces per-operation authentication, requiring re-validation for each sensitive action.

3.2 Replay Attacks
Previously captured valid requests may be reused.

Mitigation:
Time-based one-time password mechanism (TOTP, RFC 6238) prevents reuse of authentication tokens.

3.3 Privilege Escalation
Users may attempt unauthorized execution of high-privilege operations.

Mitigation:
Policy engine evaluates each request before execution.

3.4 Insider Threats
Authorized users may misuse valid sessions.

Mitigation:
Operation-level verification and audit logging.

3.5 Compromised Device Access
Attacker gains physical or remote access to an authenticated device.

Mitigation:
Continuous step-up authentication for sensitive operations.

4. Security Model
SPG follows a Zero-Trust architecture where no request is trusted by default, even after authentication.

5. Logging and Auditing
All decisions are logged for forensic analysis and traceability.
