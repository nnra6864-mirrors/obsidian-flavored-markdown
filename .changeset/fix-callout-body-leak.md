---
"@quartz-community/obsidian-flavored-markdown": patch
---

Fix nested callout body text leaking into the title when the body contains bold/italic formatting. Previously, inline nodes (e.g., `**bold**`) following a newline in a nested blockquote callout were incorrectly included in the callout title instead of the callout content.
