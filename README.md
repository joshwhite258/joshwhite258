### Hi, I'm Josh White

Controls engineer moving into software and infrastructure. On the side I build and run my own services: Python bots with tests and CI, a Proxmox home server, and ESP32 hardware. I use Claude Code as a day-to-day engineering tool, with written context and review rules for every project.

## Projects

**[ScoreBot](https://github.com/joshwhite258/ScoreBot)**: Discord bot with live scores for seven sports and an NFL model I wrote from scratch in pure Python (Elo, EPA per play, quarterback adjustments, logistic regression).
Result: picks 64% of winners on 363 held-out games, against 53% for always picking the home team. Every prediction is locked before kickoff and graded afterward, and pytest runs on GitHub Actions for every push.

**[Homelab](https://github.com/joshwhite258/Homelab)**: a retired desktop running Proxmox, with 6 VMs and containers hosting 10 services: Home Assistant, Pi-hole with Unbound, Nginx Proxy Manager, Uptime Kuma, Beszel, a Homepage dashboard deployed from git, and my Discord bots.
Result: after a 42-hour power outage showed the newest backups were two weeks old, I put guests and backups on separate drives and turned on catch-up runs, so a missed backup now runs at the next boot.

**Talking Wall Bass**: a Big Mouth Billy Bass retrofitted with an ESP32 and an audio amplifier, running ESPHome firmware.
Result: built and working. It talks and moves on command, controlled wirelessly through Home Assistant on the homelab.

**Gaming Community Event Bot**: a self-hosted Discord bot that automates member rank-ups and team competitions using third-party APIs and webhooks.
Result: runs 24/7 as a systemd service on the homelab. Private repo; demo on request.

## How I work with Claude

Full write-up with the daily schedule and diagrams: **[ai-workflow](https://github.com/joshwhite258/ai-workflow)**

- **Context as code.** Every project keeps a short CLAUDE.md (stack, deploy steps, rules, what not to touch) plus reusable skills in a private context repo, so a session starts out knowing the project.
- **Model routing.** A written guide: a small model for lookups and search, a mid-tier one for most coding, the strongest for design and review.
- **A task queue that runs itself.** I tag a Todoist task; a scheduled Claude run picks it up twice a day, does the work on a branch, and the change merges only when CI passes. Anything else waits for my review.
- **Knowledge that stays current.** A nightly GitHub Action copies each project's CLAUDE.md into a synced folder, so my Claude Projects always read the latest version.
- Next: shared agent definitions, and measuring where the routing actually saves usage.

## Contact
- joshwhite0381@gmail.com
- LinkedIn: [linkedin.com/in/joshwhite-engineer](https://linkedin.com/in/joshwhite-engineer)
