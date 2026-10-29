# Feature priorities

Prioritize safe delegation first, then visibility, then wider autonomy.

| Rank | Improvement | Reason |
| --- | --- | --- |
| 1 | Secure credential forms (#5) | Connecting an account must not put passwords or API keys in chat or model input. |
| 2 | Detailed approval rules (#6) | Owners need explicit boundaries before delegating consequential actions. |
| 3 | Advanced Auto Review (#1) | Within those boundaries, assess each action and ask when automatic review is insufficient. |
| 4 | Live execution transparency (#7) | Owners need to see what happened and intervene in the conversation. |
| 5 | Notification management (#3) | Attention should go to blocked work without interrupting for every step. |
| 6 | Multi-agent handoffs (#10) | Delegation needs clear ownership and preserved progress. |
| 7 | Group chat collaboration (#4) | Replies, mentions and reactions build on clear ownership. |
| 8 | Chief of Staff capabilities (#9) | Reliable priorities and deadlines require trustworthy agent state. |
| 9 | Proactive agents (#2) | Unprompted work needs permission boundaries and a manageable attention system. |
| 10 | Workflow learning (#8) | Learning is useful once workflows are visible, reliable and correctable. |

## First delivery

Secure credential forms already support passwords, API keys and website logins on web,
Electron and mobile. Submitted values stay outside conversation text and model input;
reusable credentials are encrypted. See [Reusable credentials](bot-secrets.md) for supported
destinations and the limits of shell variables and browser login protection.

Individual permissions use exact tool names, with Allow, Ask and Block choices. Settings can
now create a tool rule before an action happens and switch existing tool, connector and site
rules back to Ask. These changes apply to account settings or a Space's separate settings,
using the same backend on every surface. Existing block precedence, explicit human approval
requirements and Never ask mode behavior remain unchanged. A tool rule covers that tool;
it does not interpret arbitrary shell code as separate email, deletion or purchase actions.

Auto Review already assesses individual actions using the configured checker and falls back
to approval when it cannot review them. Approval cards provide Allow once, Always allow
where supported, and Deny. LLM and structured decision checkers now also ask without making
a model call when the action arguments, owner task or bot description would be truncated.
A new site's URL is still reviewed in full. This protects against approving a partial action;
it does not change the semantic risk rubric or claim new model calibration.

The remaining seven improvements are ranked follow-up work, not part of this delivery.
