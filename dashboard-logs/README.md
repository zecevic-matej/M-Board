# M-Board dashboard logs

This folder is where M-Board keeps a synced copy of your dashboard data.

## How it gets populated

Open `dashboard.html`, click the **💾** icon (or press `D`), then either:

- **Save snapshot now** — downloads `dashboard-logs-{timestamp}.zip`. Extract its `dashboard-logs/` folder into _this_ folder and you're up to date.
- **Auto-snapshot on every change** (toggle) — M-Board automatically downloads a fresh ZIP within ~2 s of every edit. Configure Safari's default download folder to this directory so the ZIPs land here automatically.
- **Live folder sync** (Chrome / Edge only) — pick this folder once and M-Board writes files here directly, no ZIPs needed.

## Files you'll find here

| File | Contents |
|------|----------|
| `contacts.json` | People: name, email, phone, photo (data URL), notes. |
| `tasks-tree.json` | Full bubble & task hierarchy. |
| `completed-history.json` | Every completed task, chronologically. |
| `daily-log.json` | Same completions grouped by day. |
| `dashboard-backup.json` | Single-file full snapshot — feed to **Import** to restore. |
| `journal.md` | **Human-readable** people directory + open tasks + daily completion diary. |

## Hand-editing `contacts.json`

You can hand-author new contacts and import them back via M-Board → **💾** → **Choose contacts file…** Minimal entry:

```json
{
  "format": "mboard-contacts-v1",
  "people": [
    { "name": "Jane Doe", "email": "jane@example.com" }
  ]
}
```

The `id` field is **optional** — it will be auto-generated if missing. Matching against existing contacts is done by `id` first, then falls back to case-insensitive name match, so you can re-import the same file repeatedly without producing duplicates.

## Individual downloads

In the **💾 Data, sync & backup** modal there's a per-file **⬇ Download** button next to each filename. Useful for re-grabbing `journal.md` for a quick read without re-downloading photos and the whole tree.

Tip: commit this folder to git for a versioned audit trail of your dashboard.
