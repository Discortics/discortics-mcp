# Discord Permission Hierarchy & Channel Security Standards

This reference establishes security standards and permission best practices when using Discortics MCP tools to create or configure Discord servers.

---

## 1. The Zero-Administrator Role Invariant

* **Never grant Administrator permissions**: When creating roles via `role.create`, the MCP service automatically creates roles with standard `permissions: "0"` (cosmetic/organizational).
* **Bot Hierarchy Rule**: The bot cannot manage, assign, or delete roles placed higher than its highest role in the Discord server hierarchy.
* **Actor Hierarchy Rule**: The user running the MCP connection cannot assign roles higher than their own highest role.
* **Dangerous Permissions Audit**:
  The bot rejects configuring roles that possess dangerous permissions (`Manage Guild`, `Manage Roles`, `Manage Channels`, `Kick Members`, `Ban Members`, `Mention Everyone`) for public self-roles or unverified members.

---

## 2. Private Staff Channel Isolation (`privateRoleIds`)

When creating private staff channels (such as `#mod-chat`, `#staff-lounge`, `#bot-alerts`, or `#review-logs`), you must explicitly declare `privateRoleIds`.

### How `privateRoleIds` Works in Discortics MCP
When `privateRoleIds` is supplied in `channel.create`:
1. The `@everyone` role overwrite is set to `DENY ViewChannel` (`0x400`).
2. Each role ID listed in `privateRoleIds` is granted `ALLOW ViewChannel`, `SendMessages`, `ReadMessageHistory`.
3. The executing bot is automatically granted explicit `ALLOW` overwrites so it can manage and deliver messages.

### Example in `propose_setup`:
```json
[
  {
    "id": "modRole",
    "kind": "role.create",
    "name": "Moderator",
    "color": 16023857
  },
  {
    "id": "staffCategory",
    "kind": "category.create",
    "name": "STAFF OPERATIONS"
  },
  {
    "id": "staffChannel",
    "kind": "channel.create",
    "name": "mod-chat",
    "parentId": "@staffCategory.channelId",
    "privateRoleIds": ["@modRole.roleId"]
  }
]
```

> [!CAUTION]
> If `privateRoleIds` is omitted, the channel will inherit parent category permissions or default to public viewable by `@everyone`. Always use `privateRoleIds` for staff, review, and audit channels.

---

## 3. Read-Only Broadcast Channels (Rules, Announcements, Info)

Broadcast channels require the public to view history but never send messages:
* Destination channels: `#rules-and-info`, `#announcements`, `#giveaways`, `#verify-here`.
* Overwrite Strategy:
  - `@everyone`: `ALLOW ViewChannel`, `ALLOW ReadMessageHistory`, `DENY SendMessages`, `DENY CreatePublicThreads`, `DENY AddReactions` (optional).
  - Staff / Bot: `ALLOW SendMessages`, `ALLOW EmbedLinks`, `ALLOW AttachFiles`.

---

## 4. Verification Gating Architecture

A robust verification gate shields the server against raids, userbots, and spam:
1. **Unverified Default**:
   - The `@everyone` role has `ViewChannel: false` on all main community channels, discussion channels, and voice lounges.
   - The `@everyone` role has `ViewChannel: true` ONLY on `#verify-here` and `#rules-and-info`.
2. **Verified Role Assignment**:
   - Create a `Verified Member` role.
   - Set all community categories/channels to grant `ViewChannel: true` to the `Verified Member` role.
   - Configure Discortics Verification module via `config.verification.update` with `roleId: "@verifiedRole.roleId"` and `channelId: "@verifyChannel.channelId"`.
   - Publish the verification panel via `config.verification.publish`.

---

## 5. Staff Application Review Channels

When setting up Discortics Staff Applications:
* Destination review channel must be a private channel with `privateRoleIds` targeting only the reviewer roles.
* Never route applicant submissions to public or semi-public channels.
* Acceptance and denial roles must be lower than the bot's highest role.

