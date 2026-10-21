---
"@opencode-ai/browser-control": patch
---

Read and write cookies in the session page's own browser profile. Chrome answers `Storage.getCookies` and `Storage.setCookies` from the most recently focused profile even when they are sent to a tab, so with several profiles open `context.cookies()` could return another profile's login. The relay now sends these as `Network.getAllCookies` and `Network.setCookies` on the routed tab. Permission commands have no tab-scoped equivalent; the README and skill note that they still follow the last-focused profile.
