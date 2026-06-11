# Open Issues

## 1. Add README.md
**Priority:** High  
**Description:** Missing project documentation. Need to explain:
- Project purpose (daily AI trend report generator)
- How to set up
- Scheduled task runs at 8 AM daily
- Report location: `C:\Users\Admin\Desktop\ai-report\`

## 2. Add .gitignore
**Priority:** High  
**Description:** Need to exclude:
- `.claude/` (local settings)
- `.git/` (already excluded by git)
- System files (.DS_Store, Thumbs.db)

## 3. Save Scheduled Task Configuration
**Priority:** Medium  
**Description:** Scheduled agent "daily-ai-trend-report" exists only in local Claude Code. 
Should document in repo:
- Schedule: 0 8 * * * (8 AM daily)
- Task prompt/logic
- Or create SKILL.md documentation

## 4. Add LICENSE
**Priority:** Low  
**Description:** Add MIT or Apache 2.0 license file
