# LINBSYNC

A collaborative workspace for notes, tasks, Kanban and comments in Obsidian.

## Install

Requires Obsidian 1.8 or later.

1. Download **main.js**, **manifest.json** and **styles.css** from the same [release](https://github.com/LINB-DEV/SYNC-PUBLIC/releases/latest).
2. Place the files in `<vault>/.obsidian/plugins/linb-sync/`.
3. Open **Settings → Community plugins** and enable **LINBSYNC**.

To update, back up your vault, disable LINBSYNC, replace the three files and enable it again. Keep your existing `data.json` to preserve settings.

## Sign in and join

When you first enable LINBSYNC, or choose **Sign in with LINB ID**, your browser opens [LINB ID](https://id.linb.org) to sign in or create an account.

Joining the shared vault requires an invitation from its owner. Enter the vault invitation in plugin settings before signing in. A LINB ID registration invitation and a vault invitation are separate; creating an account does not grant access to shared notes. Existing members can sign in without a new invitation.

For your first connection, use a new, empty vault named **Linb Vault**. Shared content will download after you sign in.

## Your data

LINBSYNC reads and updates notes and attachments in the connected vault to keep them synchronized. Shared content is available to other admitted members. Only connect content you intend to share, and back up important notes.

The plugin connects to `sync.linb.org` and uses `id.linb.org` for sign-in. Connections are encrypted in transit; shared content is not end-to-end encrypted by default. Your session is saved on this device. Your LINB ID password and Passkey are not stored by the plugin. Signing out does not delete downloaded files.

There is no analytics or advertising tracking. Audio recording requests microphone access when used. LINBSYNC is independent of Obsidian Sync.

## Support

[Report a problem](https://github.com/LINB-DEV/SYNC-PUBLIC/issues). Do not include passwords, session tokens, invitation codes or private notes.

## License

See [LICENSE](LICENSE). Third-party license notices are included in the plugin.
