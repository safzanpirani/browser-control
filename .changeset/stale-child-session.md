---
"@opencode-ai/browser-control": patch
---

Stop `page.unroute()`, `page.route()` and similar page-wide calls failing with `Session with given id not found` after a navigation tears down a frame or worker. When Chrome no longer knows a child session, the relay now detaches it before returning the error, so Playwright skips the dead child instead of failing the whole call.
