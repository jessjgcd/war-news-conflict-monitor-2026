# My n8n Workflows Collection

A personal backup and showcase of my n8n automation workflows (JSON exports). Built for practice, news monitoring, GitHub management, and more.

All workflows are free to use/modify (MIT license implied unless noted). Self-host n8n Community Edition required.

## War & Conflict News Monitor (2026 Edition)

**File:** [news-monitoring/war-news-conflict-monitor.json](./news-monitoring/war-news-conflict-monitor.json)

**What it does (simple):**
- Runs daily at 8 AM.
- Pulls fresh RSS from Al Jazeera, BBC World, and The Guardian.
- Filters for war/conflict-related news (Ukraine, Gaza, Sudan, etc.).
- Scrapes full clean article text using Jina.ai Reader.
- Detects **conflicts** (e.g., "disputed" or "clashing reports" in text).
- Detects **urgent escalations** (e.g., "strike", "killed", "war crime").
- Sends Telegram alerts:
  - Normal summary 📰
  - Conflict warning ⚠️
  - Urgent escalation 🚨
- Saves everything to Supabase for history/search.

**Requirements / Setup:**
- n8n (self-hosted, free)
- Telegram bot token + chat ID
- Supabase project (free tier) → table: `war_news` (columns: id, title, url, source, full_text, conflict_flag, created_at)
- No paid services needed for light use

**How to import:**
1. Download the JSON file.
2. In n8n → ... → Import from File → select it.
3. Add credentials for Telegram & update Supabase URL/key.
4. Activate & test!

**Why this workflow?**
Great for staying informed on global conflicts with smart filtering and conflict detection — all automated and free.

More workflows coming soon...

## Other Workflows

- **GitHub Issue Claim with Conflict Check** → [github-tools/github-issue-claim-conflict.json](./github-tools/github-issue-claim-conflict.json)  
  Auto-assigns issues on "assign me" comment, notifies if already taken.

## License
MIT – feel free to copy, modify, share.

Questions or improvements? Open an issue or fork!

Last updated: March 2026
