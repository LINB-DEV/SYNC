# LINB

A collaborative workspace for Obsidian: synchronized notes, tasks, Kanban boards and comments, using your LINB ID.

## Getting started

1. Install the plugin in Obsidian 1.8 or later and enable it. On first enable, the plugin opens the LINB ID sign-in page in your browser. You can also choose **Sign in with LINB ID** from the command palette or **Sign in with LINB ID** in plugin settings.
2. Sign in or create an account at [LINB ID](https://id.linb.org). Account registration may require an ID invitation, according to the current registration policy.
3. Access to the shared vault requires a separate invitation from its owner. After signing in and authorizing LINB ID, enter the vault invitation on the browser page. Registering a LINB ID does not grant access to the vault.
4. Confirm the request in your browser and return to Obsidian. The current vault joins the shared library; a new empty vault or a specific vault name is not required. Files in this vault become shared with admitted members.

Existing members can sign in again without an invitation. The vault owner can create one-use, expiring invitations in member management. The existing owner uses their LINB ID.

For simultaneous editing of a LINB rich document (`.1inb`), update every participating device to 0.5.8 or later. Existing recovery copies are kept so you can compare their contents.

## Installation before Community review

Download `main.js`, `manifest.json` and `styles.css` from the same [release](https://github.com/LINB-DEV/SYNC-PUBLIC/releases). Put them in `<vault>/.obsidian/plugins/linb-sync/`, then enable **LINB** under Community plugins. The plugin ID is `linb-sync`. A GitHub release does not mean the plugin has been accepted into the Obsidian Community directory.

## Network, accounts and privacy

- This is the client for the LINB shared service. Synchronization requires internet access, a LINB ID and admission to the shared vault.
- Authentication opens `id.linb.org`. The plugin talks to `sync.linb.org` over HTTPS and secure WebSocket. Passwords, Passkeys and the confidential OIDC client secret are not stored in the plugin. The plugin retains its SYNC session token in Obsidian plugin data while signed in.
- Connecting synchronizes shared-vault content and attachments with the service and other admitted members. Treat content placed in that vault as shared. Transport is encrypted; the shared vault is **not end-to-end encrypted by default**.
- Local working state is stored in the vault and browser storage used by Obsidian. Back up valuable notes before connecting. Signing out does not erase already downloaded files.
- Audio recording features ask for microphone permission when used. The plugin does not implement analytics, advertising telemetry, or its own plugin updater.
- LINB is independent of the official Obsidian Sync service. This private source repository contains only the Obsidian client; service implementation, deployment configuration and credentials are not included.

## Build from source

Use Node.js 22 or later:

```sh
npm ci
npm run check
npm run build
```

The build produces readable `main.js`, `manifest.json`, `styles.css` and `THIRD-PARTY-NOTICES.txt` at the repository root. It rejects server modules and Node-only runtime APIs in the client bundle. Releases use a tag matching the manifest version exactly (for example `0.5.1`). No production credentials are needed to build.

## License and support

MIT; see [LICENSE](LICENSE) and [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt). The incorporated Kanban code retains its original license in `plugin/src/kanban/LICENSE`.

Report issues in this repository. Never include session tokens, invitations, private notes or credentials in an issue.


## Sign-in and offline access

LINB ID sign-in is required before workspace features are activated. Signed-in devices keep working offline. Signing out or receiving a session-revocation response disables the plugin features without deleting local documents. An offline device learns about remote revocation when it reconnects.


## Document sharing and PDF export

In a LINB document, open **Share document** to publish a read-only web link. **Anyone with the link** can view without joining your shared vault. **Invited members only** requires a selected shared-vault member to sign in with LINB ID. Editing stays in the original vault. You can copy the latest link and revoke your published links, including links created on another device. Changing a draft does not change existing links. Links expose only the original document and its referenced images, not the entire vault. There is no save-copy or import action.

**Export PDF** is available on desktop and mobile. Mobile rendering is local and offers **Save to vault** (`Exports/`, with unique filenames) and system file sharing where supported. Mobile PDF pages are images, so their text is not selectable. No document is uploaded for PDF rendering.
