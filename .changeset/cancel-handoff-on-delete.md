---
"@opencode-ai/browser-control": patch
---

`session delete` and `session reset` no longer time out while an execute is blocked in `handoff()`. They cancel the pending handoff, the execute fails with "Handoff cancelled because its session was deleted" (or reset), and the delete or reset then proceeds. Before, the session stayed locked until someone found the tab and pressed Continue.
