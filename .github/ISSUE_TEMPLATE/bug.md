---
name: Bug Report
about: Report a bug or issue
---

## Issue: Reduce unnecessary WebFetch permissions in settings.local.json

### Problem
`settings.local.json` contains 21 domain whitelists for WebFetch that are not used by the scheduled agent.

### Current State
- WebFetch permissions for: evertune.ai, huggingface.co, github.com, arxiv.org, pypi.org, and 16 others
- Scheduled agent only uses: WebSearch (no WebFetch needed)

### Solution
Remove all unnecessary WebFetch permissions to minimize permission exposure.

### Changes Made
- ✅ Cleaned up settings.local.json to keep only WebSearch
