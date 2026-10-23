---
"@opencode-ai/browser-control": patch
---

Refuse `context.grantPermissions()` and `context.clearPermissions()` when no window of the session's Chrome profile is focused. Chrome applies permission commands to the most recently focused profile, so with several profiles open they could change another profile's permissions. The extension now reports its profile's focus through a `windows.focusState` capability; relays talking to older extension builds forward these commands unchanged.
