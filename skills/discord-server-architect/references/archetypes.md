# Discord Server Thematic Archetypes & Design Blueprints

This reference provides production-ready blueprints for popular Discord server themes. Each archetype includes curated category structures, channel trees, aesthetic naming conventions, hex color palettes, role hierarchies, self-role options, and onboarding configurations.

---

## 1. Gaming & Esports Clan / Community

Ideal for: Competitive teams, gaming clans (Valorant, CS2, Overwatch, Apex, League), or multi-game community hangouts.

### Aesthetic Palette
* **Primary / Clan Leader**: `#E63946` (Crimson Red)
* **Officer / Moderator**: `#F4A261` (Warm Amber)
* **Team Captains / VIP**: `#2A9D8F` (Teal)
* **Active Members / Clan Member**: `#457B9D` (Steel Blue)
* **Guest / Unverified**: `#99AAB5` (Discord Muted)

### Category & Channel Hierarchy

```
📁 ─── INFO & RULES ───
  ├─ 📌・rules-and-info          (Read-only; server rules, clan manifesto)
  ├─ 📢・announcements           (Read-only; official clan updates)
  ├─ 🎁・giveaways               (Read-only; community giveaways & tournaments)
  └─ 🔑・verify-here             (Verification panel destination)

📁 ─── COMMUNITY HUB ───
  ├─ 💬・general-chat            (Primary text chat)
  ├─ 🤖・bot-commands            (Level checking, mini-games, music)
  ├─ 🎭・memes-and-media         (Media, clips, screenshots)
  ├─ 🌟・starboard               (Best clips & community highlights)
  └─ 💡・suggestions             (Community ideas & voting)

📁 ─── LFG & RECRUITMENT ───
  ├─ 🎮・lfg-competitive         (Looking for team/competitive stacks)
  ├─ 🎯・lfg-casual              (Casual game lobbies)
  └─ 🏆・scrims-and-tourneys     (Organized scrim schedules)

📁 ─── VOICE LOUNGES ───
  ├─ 🔊・Squad Alpha (Voice)
  ├─ 🔊・Squad Bravo (Voice)
  ├─ 🔊・Casual Hangout (Voice)
  └─ 🔇・AFK Lounge (Voice)

📁 ─── SUPPORT & STAFF ─── (Private: privateRoleIds: ["@modRole.roleId", "@officerRole.roleId"])
  ├─ 🎫・open-a-ticket           (Ticket deployment panel for appeals & reports)
  ├─ 🛡️・staff-lounge            (Private moderator chat)
  ├─ 📋・mod-logs                (Audit and moderation actions)
  └─ 🚨・bot-alerts              (Anti-Nuke and AutoPilot alerts)
```

### Module Orchestration
1. **Verification**: Enabled with Rules screening in `🔑・verify-here`.
2. **Self Roles**: Select dropdown in `📌・rules-and-info` for Game Roles (Valorant, CS2, Apex, League) and Ping Roles (Announcements, Giveaways, Tournaments).
3. **Tickets**: Panels for "Player Report", "Clan Recruitment", and "General Support".
4. **AutoPilot**: Anti-spam, anti-invite links (except clan domains), and raid threshold set to High.
5. **Levels / XP**: Custom XP curve with Level 5, Level 15, and Level 30 cosmetic rank badges.

---

## 2. Creator, Streamer & Media Studio

Ideal for: Twitch streamers, YouTubers, TikTok creators, podcasters, and artists.

### Aesthetic Palette
* **Creator / Host**: `#9D4EDD` (Vibrant Purple)
* **Mod Squad**: `#7B2CBF` (Deep Violet)
* **Twitch Subscribers / VIPs**: `#FFB703` (Golden Honey)
* **Super Boosters**: `#F72585` (Hot Pink)
* **Community Members**: `#4CC9F0` (Electric Cyan)

### Category & Channel Hierarchy

```
📁 ─── WELCOME & SOCIALS ───
  ├─ 🚀・welcome-and-rules       (Components V2 welcome layout + guidelines)
  ├─ 🔴・live-streams            (Automated Twitch / YouTube notifications)
  ├─ 🎬・new-videos              (Automated YouTube / TikTok uploads)
  └─ ⭐・role-select             (Self-roles for stream alerts)

📁 ─── CHAT & SHOWCASE ───
  ├─ ☕・main-chat               (General discussion)
  ├─ 🎨・fan-art-and-media       (Art showcase, fan submissions)
  ├─ 🍿・stream-clips            (Viewer clips and funny moments)
  ├─ 🎵・music-and-vibes         (Playlist sharing, Spotify listening)
  └─ 💬・confessions             (Anonymous community confessions)

📁 ─── SUBSCRIBER LOUNGE ─── (Private: privateRoleIds: ["@subRole.roleId", "@boosterRole.roleId"])
  ├─ 💎・sub-vip-chat            (Exclusive chat with creator)
  └─ 🔊・Sub VIP Voice (Voice)

📁 ─── COMMUNITY VOICE ───
  ├─ 🎙️・Stream Hangout (Voice)
  ├─ 🎮・Community Gaming (Voice)
  └─ 💤・AFK (Voice)

📁 ─── STUDIO OPS ─── (Private: privateRoleIds: ["@modRole.roleId"])
  ├─ 🎫・support-and-collabs     (Ticket panel: Collabs, Business, Moderation)
  ├─ 📝・mod-chat                (Staff discussions)
  └─ 📊・audit-log               (System alerts)
```

### Module Orchestration
1. **Notifications**: Auto-feed Twitch / YouTube live events into `🔴・live-streams`.
2. **Booster Perks**: Custom Embed/Components V2 celebratory boost message in `☕・main-chat`.
3. **Starboard**: Threshold set to 5 ⭐ reactions routed to a dedicated highlight channel.
4. **Self Roles**: Reaction/Button panel for "Live Stream Pings", "Upload Pings", and "Event Pings".

---

## 3. Developer, Tech & Open Source Project

Ideal for: Software engineers, open-source repositories, startups, hackathons, and API ecosystems.

### Aesthetic Palette
* **Core Maintainer / Founder**: `#5865F2` (Blurple)
* **Triager / Moderator**: `#57F287` (Mint Green)
* **Contributors**: `#FEE75C` (Solar Yellow)
* **Developers / Builders**: `#EB459E` (Fuchsia)
* **Community Members**: `#3BA55D` (Dark Emerald)

### Category & Channel Hierarchy

```
📁 ─── GETTING STARTED ───
  ├─ 📜・rules-and-conduct       (Code of Conduct, contribution guidelines)
  ├─ 📢・releases-and-news       (GitHub releases, changelog, status updates)
  ├─ 🚀・getting-started         (Documentation links, quickstart guides)
  └─ 🏷️・tech-stack-roles        (Self-roles for programming languages)

📁 ─── DEVELOPMENT & DISCUSSIONS ───
  ├─ 💬・general-dev             (General software engineering talk)
  ├─ 🛠️・project-showcase        (Show off projects built with the stack)
  ├─ 💡・rfc-and-proposals       (Feature discussions, architecture feedback)
  └─ 🤖・bot-playground          (API tests, bot experimentation)

📁 ─── TOPIC FORUMS / CHANNELS ───
  ├─ 🐍・python-and-backend      (Python, Go, Node.js, databases)
  ├─ ⚛️・frontend-and-ui         (React, Vue, Tailwind, UX)
  ├─ 🦀・rust-and-systems        (Rust, C++, low-level engineering)
  └─ 🧠・ai-and-ml               (LLMs, agents, embeddings, data science)

📁 ─── COLLABORATION VOICE ───
  ├─ 🔊・Pair Programming (Voice)
  ├─ 🔊・Office Hours (Voice)
  └─ 🔊・Audio Lounge (Voice)

📁 ─── MAINTAINER OPERATIONS ─── (Private: privateRoleIds: ["@maintainerRole.roleId"])
  ├─ 🎫・issue-and-support       (Ticket panel: Bug Reports, Security, Contributor Inquiries)
  ├─ 📝・maintainer-sync         (Internal engineering sync)
  └─ 🛡️・security-reports        (Responsible disclosure intake)
```

### Module Orchestration
1. **Self Roles**: Multi-select dropdown for language & framework tags (Python, TypeScript, Rust, Go, React).
2. **Applications**: Form for "Contributor / Triager Onboarding" with coding portfolio questions.
3. **Tickets**: Panels with structured intake questions (Reproduction steps, OS, logs).
4. **Anti-Nuke**: Maximum protection against unauthorized role or webhook changes.

---

## 4. Anime, Cozy & Aesthetic Lounge

Ideal for: Aesthetic social hubs, anime fans, study cafes, and chill hangout spots.

### Aesthetic Palette
* **Café Owner**: `#FFB5A7` (Muted Rose)
* **Barista / Staff**: `#FCD5CE` (Blush Cream)
* **Regulars / VIP**: `#F8EDEB` (Soft Pearl)
* **Coffee Lovers / Members**: `#D8E2DC` (Sage Mist)
* **New Arrivals**: `#ECE4DB` (Warm Linen)

### Category & Channel Hierarchy

```
📁 ─── ˗ˏˋ ☕・INFO & MENU ˎˊ˗ ───
  ├─ 📜・rules-and-welcome       (Warm aesthetic welcome & cozy rules)
  ├─ ☕・role-counter            (Pronouns, color roles, hobby pings)
  └─ 🌸・announcements           (Café news, community events)

📁 ─── ˗ˏˋ 🍵・THE CAFE CHAT ˎˊ˗ ───
  ├─ 💬・lounge-chat             (Cozy everyday chatter)
  ├─ 📷・daily-moments           (Photos of pets, food, coffee, nature)
  ├─ 🎨・art-and-aesthetic       (Visual inspiration, drawings, edits)
  ├─ 💌・confessions             (Anonymous sweet messages & confessions)
  └─ 🌟・hall-of-fame            (Starboard for wholesome messages)

📁 ─── ˗ˏˋ 📚・STUDY & FOCUS ˎˊ˗ ───
  ├─ 📖・study-and-work          (Productivity accountability, goals)
  ├─ 🎵・music-recommendations   (Lo-fi playlists, soundtrack shares)
  └─ 🔇・Quiet Study Room (Voice)

📁 ─── ˗ˏˋ 🧁・STAFF BACKROOM ˎˊ˗ ─── (Private: privateRoleIds: ["@staffRole.roleId"])
  ├─ 🎫・help-desk               (Ticket panel for friendly member support)
  └─ 🍵・staff-tea               (Internal staff chat)
```

### Module Orchestration
1. **Welcome Message**: Customized Embed with cute typography, greeting card, and member count tracker.
2. **Economy**: Virtual coffee beans / currency with a café shop item catalogue (Custom color badges, role perks).
3. **Starboard**: Whimsical star emoji with sweet highlight embeds.
4. **Confessions**: Configured in anonymous mode with logging in staff backroom.

---

## 5. Web3, DAO & Crypto Guild

Ideal for: Token communities, NFT holders, protocol DAOs, and crypto research collectives.

### Aesthetic Palette
* **Core Council**: `#00F0FF` (Cyber Neon)
* **Stewards / Moderators**: `#7928CA` (Electric Indigo)
* **Alpha Researchers**: `#FF0080` (Fluorescent Magenta)
* **DAO Members**: `#0070F3` (Vercel Blue)
* **Prospects**: `#888888` (Titanium Grey)

### Category & Channel Hierarchy

```
📁 ─── 🔐 ONBOARDING & SECURITY ───
  ├─ 🛡️・verify-identity         (Strict verification gate to protect against drainer bots)
  ├─ 📜・constitution-and-rules  (Governance guidelines, security notices)
  ├─ 🚨・official-links-only     (Read-only locked channel for contract addresses & domains)
  └─ 📢・governance-alerts       (Proposals, Snapshot votes, major releases)

📁 ─── 🌐 THE PLAZA ───
  ├─ 💬・general-discussion      (Market chat, macro, ecosystem talk)
  ├─ 📊・governance-debates      (Discussion on active proposals)
  ├─ 🧠・research-and-alpha      (In-depth protocol analysis, technical breakdowns)
  └─ 💡・ideas-and-feedback      (DAO improvement suggestions)

📁 ─── 🤝 GUILDS & WORKING GROUPS ───
  ├─ 🛠️・dev-guild               (Smart contracts, frontend, audits)
  ├─ 🎨・creative-guild          (Branding, memes, content creation)
  └─ 📈・growth-guild            (Partnerships, marketing, community)

📁 ─── 🔒 COUNCIL CHAMBERS ─── (Private: privateRoleIds: ["@councilRole.roleId", "@stewardRole.roleId"])
  ├─ 🎫・dao-support             (Ticket panel: Multi-sig support, Partnership intake)
  ├─ 🛡️・council-discussion      (Core team strategy)
  └─ 🚨・security-audit-logs     (Anti-Nuke trigger alerts)
```

### Module Orchestration
1. **Verification**: Mandatory verification gate; all discussion channels locked until verified.
2. **AntiNuke & Autopilot**: MAXIMUM lockdown. Anti-phishing links, automatic mass-mention quarantine, burst threshold protection.
3. **Tickets**: Multi-sig verification and private partnership intake.
4. **Automations**: Notification webhooks on new governance votes or contract alerts.

