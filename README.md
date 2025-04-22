# Discord Content Management System
## a Discord-Backend Static Web System

**Welcome to the beginning of something wild.**  
This project is a radical rethink of what a “backend” actually is — no servers, no databases, no APIs in the traditional sense. Instead, we use [Discord](https://discord.com/) as our backend, and a [static site hosted on GitHub Pages](https://pages.github.com/) as the frontend. That’s it.

---

## Vision

To create a fully-functional, modular, hackable **backendless web system**, where **Discord is the database, file system, CMS, and control panel** — and a static site becomes the real-time interface that renders and interacts with it.

This is:
- A new kind of **low-cost, high-leverage infrastructure**.
- A toolset for **non-technical users to operate web platforms** through Discord.
- A sandbox for **hyper-flexible workflows** built from existing tools.

No backend. No hosting bills. Full power.

---

## Philosophy

- **Own the stack** without maintaining one.
- **Abuse free infrastructure with precision.**
- **Turn Discord into programmable state**.
- **Let humans operate the system, not configure it.**
- **Minimize friction. Maximize leverage.**

---

## Features (Implemented / Planned)

### Core Features

- [x] Fetch and render messages from Discord as structured content (shop items, blog posts, news).
- [x] Parse attachments from Discord channels as assets (images, PDFs, videos, etc).
- [x] Allow admins to edit content by editing messages.
- [ ] Render Discord messages as JSON for API-style consumption.
- [ ] Markdown support in Discord → formatted content on site.
- [ ] Caching layer in JS to reduce Discord API calls and rate limits.
- [ ] Use message metadata (timestamps, authors, reactions) as structured data.

---

## Use Case Modules

### Shop System
- Each item = message in `#shop-items`.
- Fields: name, price, description, image attachment.
- Editable in Discord, renders live on the site.
- Future: emoji reactions to upvote/rate items, out-of-stock tags.

### File Vault
- Upload files to `#files` or `#assets`.
- Frontend renders gallery/download center.
- Auto-group files based on message tags.

### Blog / News Posts
- Message = post. Markdown supported.
- Attach images for post banners.
- Can schedule posts by timestamp.

### Public Task Board
- Users submit tasks to `#tasks`, admins approve/respond.
- Site shows live tasks and statuses.
- Could evolve into a freelance or bounty system.

### Polls & Voting
- Create polls with emoji-based voting.
- Frontend parses reaction counts and renders charts.
- Could power community decisions or open governance.

### Public Config System
- `#config` channel defines site-wide variables:
  ```
  [title] My Awesome Project
  [theme-color] #ff3366
  ```
- Parsed on load, affects global layout/colors/settings.

### Micro SaaS Toolkit (planned)
- Users interact with Discord to trigger small tools:
  - URL shortener
  - Text-to-speech
  - Image compressors
  - QR code generators
- Tools powered by bot actions, results served via site.

### Public Guestbook / Testimonials
- Visitors submit quotes, stories, or feedback to a channel.
- Auto-curated and rendered into a scrolling testimonials section.

### Frontend-less APIs for Real-World Interaction
- React in a channel → trigger real-world IoT actions.
- Control hardware (e.g. 3D printers, coffee machines) via Discord.

### Human Intelligence Network
- Task requests in Discord, solved by human agents.
- Frontend renders answers — like a distributed knowledge API.

### Configurable Website
- Modify site title, colors, layout from Discord messages.
- Dynamic updates on frontend with no deploy required.

### Social Ledger / Activity Feed
- Messages + reactions = public record.
- Acts like a transparent, editable blockchain for task/project tracking.

---

## Long-Term Crazy Goals

- **Human-to-human app platform**: Let users run apps inside Discord and the results appear on the site.
- **IoT Control Panel**: Site reacts to reactions in a `#iot-control` channel that trigger real-world devices.
- **Public Knowledgebase**: Like a wiki, but all content is stored and edited via Discord.
- **Programmable API layer over Discord messages**.
- **Fully reactive frontend using WebSockets + Discord bots** (stretch goal).

---

## Architecture

```
GitHub Pages (Static Site)
        |
     HTML / JS
        |
  Discord Bot API (read-only)
        |
 Discord Server (channels = data)
```

No databases. No auth system. No cloud infrastructure.

---

## How It Works

1. Admin posts/edit messages in specific Discord channels.
2. Frontend fetches data using a bot token and Discord API.
3. Messages are parsed into structured data (using custom tags or formats).
4. JS renders that data into components (cards, tables, galleries, etc).
5. User sees a dynamic site that’s controlled entirely from Discord.

---

## Setup

1. Create a Discord bot, add it to your server with `Read Messages` and `Read Message History`.
2. Note your bot token and target channel IDs.
3. Clone this repo and update the JS config with your token and channel IDs.
4. Push to GitHub — GitHub Pages will deploy your site automatically.
5. Start managing the site from inside Discord.

---

## Roadmap

| Phase | Goal |
|-------|------|
| **Phase 1** | Static site + Discord as data storage (blog, shop, files) |
| **Phase 2** | More interactivity: polls, public submissions, config |
| **Phase 3** | Micro SaaS tools, bot-triggered actions |
| **Phase 4** | Human-powered API, automation, programmable systems |
| **Phase 5** | Fully decentralized public utility app — Discord = backend OS |

---

## Methods & Hackery

- **Message format conventions**: Use simple syntax to define structure, e.g.:
  ```
  [title] Big Red Hoodie
  [price] $25
  [desc] It's soft and glorious.
  ```
- **CDN abuse**: Every uploaded image/file is hosted forever on Discord’s CDN — we just need the attachment URLs.
- **Rate limit avoidance**: Use caching, pre-fetching, and smart throttling. Store Discord data locally or in `localStorage` if needed.
- **Botless read-only mode** (possible): Use webhooks or public message embeds for basic fetching.

---

## Contribution

This isn’t just a project — it’s an experiment. Fork it, remix it, extend it, break it. Try wild shit. Use Discord as a DB, API, file system, config manager, and social graph.

If you have an idea for a crazy module or use case, open an issue or make a PR.

---

## License

MIT — abuse responsibly.

---

## Final Word

We’re building the **most powerful web platform possible using no backend at all**.

If we pull this off, this becomes:
- A new dev stack.
- A new way to think about CMSes.
- A tool for bootstrapping entire platforms with no cost, instantly.

Let’s make Discord do things it was never meant to do.

---
