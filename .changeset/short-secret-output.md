---
"@opencode-ai/browser-control": patch
---

Stop rewriting short known values in execute and `secrets run` output. A captured cookie or field such as `count=1` used to turn every `1` in later output into `${BC_SECRET_N}`, so `Flat 30% off` read `Flat 3${BC_SECRET_9}% off`. Values shorter than six characters remain profile slots and artifact references but are no longer redacted from output.
