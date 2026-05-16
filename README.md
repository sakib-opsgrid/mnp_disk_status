# MNP Status Reporter

Web-based dashboard that converts raw Nagios monitoring output into a clean, structured report — with one-click copy for WhatsApp.

## Files

```
├── index.html   — App UI (input + report screens)
├── style.css    — Web-first dashboard styles
├── app.js       — Parser, renderer, export logic
└── README.md    — This file
```

## Deploy to GitHub Pages

1. Create a new **public** repo (e.g. `mnp-reporter`)
2. Upload all 4 files to the repo root
3. Go to **Settings → Pages → Branch: main → Save**
4. Live at: `https://<username>.github.io/mnp-reporter/`

## Report Rules

| Rule | Detail |
|------|--------|
| Disk | Only partitions with free space **≤ 20%** included |
| Disk format | `partition MB (free% inode=inode%)` |
| Multiple partitions | All qualifying partitions per server |
| Memory | Always included — shows used MB and % |
| Swap | Always included — shows free MB and % |
| Deduplication | One entry per host per service type |
| Hostname | Any prefix accepted |
| Unsupported services | PING, HTTP, SSH etc. silently skipped |
| Time | Snapped to nearest slot: **09:00 AM** or **06:00 PM** |

## Keyboard Shortcut

`Ctrl + Enter` (or `Cmd + Enter` on Mac) inside the textarea → Generate
