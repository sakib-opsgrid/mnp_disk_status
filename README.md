# MNP Status Reporter

Mobile-first web tool that converts raw Nagios monitoring output into a clean report — ready to paste directly into WhatsApp.

## Files

```
├── index.html   — App UI (input + report screens)
├── style.css    — Mobile-first responsive styles
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
| Multiple partitions | All qualifying partitions per server on one line |
| Disk format | `partition MB (free% inode=inode%)` |
| Memory | Always included — shows used MB and % |
| Swap | Always included — shows free MB and % |
| Deduplication | One entry per host per service type |
| Hostname | Any prefix accepted — not limited to `prod` |
| Unsupported services | PING, HTTP, SSH etc. are silently skipped |
| Time | Snapped to nearest slot: **09:00 AM** or **06:00 PM** |

## Keyboard Shortcut

`Ctrl + Enter` (or `Cmd + Enter` on Mac) inside the textarea → Generate
