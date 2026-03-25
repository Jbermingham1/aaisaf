# Checklist 04 — MCP & Tool Security

**Applicable System Types:** C, F, G

## Quick Assessment Items (marked with Q)

| # | Check | Quick | Standard | Deep | Technique |
|---|-------|-------|----------|------|-----------|
| 4.1 | Verify MCP server allowlist exists and is enforced | Q | X | X | TA10.009 |
| 4.2 | Review all MCP tool descriptions for hidden instructions | Q | X | X | TA10.001 |
| 4.3 | Verify MCP servers are authenticated (not open to unauthenticated access) | Q | X | X | TA10.008 |
| 4.4 | Verify MCP servers are bound to localhost or have network restrictions | Q | X | X | TA10.008 |
| 4.5 | Check if tool descriptions are version-pinned (rug pull protection) | | X | X | TA10.002 |
| 4.6 | Scan tool descriptions for references to other tools (shadowing) | | X | X | TA10.003 |
| 4.7 | Test for cross-origin prompt injection via MCP resource content | | X | X | TA10.004 |
| 4.8 | Test tool chaining for privilege escalation | | X | X | TA10.005 |
| 4.9 | Test for SSRF via MCP tool parameters (internal IPs, cloud metadata) | | X | X | TA10.006 |
| 4.10 | Test for data exfiltration via tool output channels | | X | X | TA10.007 |
| 4.11 | Test tool argument injection (path traversal, command injection) | | X | X | TA10.010 |
| 4.12 | Verify MCP transport encryption (TLS for non-localhost) | | X | X | TA10.011 |
| 4.13 | Assess consent fatigue risk (approval frequency, UI design) | | X | X | TA10.012 |
| 4.14 | Full MCP server enumeration and attack surface mapping | | | X | All TA10 |
| 4.15 | Attempt malicious MCP server registration | | | X | TA10.009 |
| 4.16 | Test transport-level message injection/replay | | | X | TA10.011 |

## Evidence Requirements

- MCP server configuration file listing
- Tool description content (full JSON)
- Network binding evidence (listening addresses)
- Authentication mechanism documentation
- Successful/failed privilege escalation chain documentation
