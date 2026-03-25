# Checklist 03 — Agent & Orchestration Security

**Applicable System Types:** C, D, G

| # | Check | Quick | Standard | Deep | Technique |
|---|-------|-------|----------|------|-----------|
| 3.1 | Verify tool invocation is restricted to an allowlist | Q | X | X | TA03.001 |
| 3.2 | Test for unauthorised tool invocation via prompt manipulation | | X | X | TA03.001 |
| 3.3 | Test agent goal hijacking (redirect agent to attacker objective) | | X | X | TA03.002 |
| 3.4 | Verify human-in-the-loop controls for destructive actions | Q | X | X | TA03.007 |
| 3.5 | Test privilege escalation through agent delegation (if multi-agent) | | X | X | TA03.006 |
| 3.6 | Verify inter-agent communication validation (if multi-agent) | | X | X | TA03.003 |
| 3.7 | Test memory poisoning in persistent agents | | X | X | TA03.004 |
| 3.8 | Test cascading failure scenarios (if multi-agent) | | | X | TA03.005 |
| 3.9 | Test autonomous action boundaries (what can the agent do without approval?) | Q | X | X | TA03.007 |
| 3.10 | Test agent impersonation in multi-agent systems | | | X | TA03.008 |
| 3.11 | Test planning phase manipulation | | X | X | TA03.009 |
| 3.12 | Review feedback loop security | | X | X | TA03.010 |
| 3.13 | Verify agent permission scoping (least privilege) | Q | X | X | TA03.006 |
| 3.14 | Full adversarial agent exploitation scenario | | | X | All TA03 |

## Evidence Requirements

- Tool allowlist configuration
- Agent permission scoping documentation
- Human-in-the-loop control evidence
- Memory persistence mechanism documentation
- Agent delegation chain documentation (multi-agent)
