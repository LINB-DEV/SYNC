# LINB Sync

Collaborative notes, tasks, Kanban and comments in Obsidian, with invite-only synchronization through LINB ID.

## Install

Download **main.js**, **manifest.json** and **styles.css** from the same [release](https://github.com/LINB-DEV/SYNC/releases). Place them in `<vault>/.obsidian/plugins/linb-sync/` and enable **LINB Sync**. Requires Obsidian 1.8 or later. The plugin ID is `linb-sync`.

For 0.5.0 users: disable the old plugin, back up its folder, rename `quiet-sync` to `linb-sync`, keep `data.json`, and replace the three release files. Do not run both copies.

On first enable, or when you choose **Sign in with LINB ID**, your browser opens [LINB ID](https://id.linb.org) for registration/sign-in and confirmation. First connection uses a new, empty **Linb Vault**. Existing notes are checked before joining to avoid unintended merging.

Account registration may require an ID invitation. Joining the shared vault requires a **separate, one-use vault invitation from its owner**. Enter it in plugin settings before signing in. Registering a LINB ID alone does not grant access to shared notes. Existing members can sign in again without an invitation.

## Privacy and network access

The plugin connects to `sync.linb.org` over HTTPS/WebSocket and authenticates at `id.linb.org`. It keeps the SYNC session token in local plugin data. It never stores your ID password, Passkey or the service's confidential OIDC secret.

Synchronization enumerates files in the connected vault and reads/writes notes and attachments through the Obsidian API. Enumeration is needed to reconcile shared files, indexes and imports. Shared content is sent to the service and other admitted members. Transport is encrypted; the shared vault is **not end-to-end encrypted by default**. Only connect a vault whose content you intend to share. Back up valuable notes first. Signing out does not remove downloaded files.

There is no analytics, advertising telemetry or separate plugin updater. Audio recording asks for microphone permission when used. LINB Sync is independent of official Obsidian Sync.

## Private-source review

This public repository distributes installable assets and documentation only. TypeScript/CSS source and build configuration are in the private `LINB-DEV/SYNC-SOURCE` repository, with the **same release tag**. The owner must grant the Obsidian Community GitHub App access and select that source repository in the submission. A private-source reviewed badge appears only after Obsidian independently reproduces the public main.js. A GitHub release or a passing local lint run does not mean Community approval.

The compiled JavaScript is necessarily public so Obsidian can load it. Source that was publicly available in version 0.5.0 cannot be recalled from copies already made.

## 0.5.1 review fixes

Corrected the plugin ID; preserved workspace leaf positions on unload; replaced static style assignments and manual settings headings; removed clipboard innerHTML assignment and iOS-incompatible regexp lookbehind; fixed the author URL, explicit lib0 dependency, CSS overrides and duplicate top declaration. Required third-party license notices are embedded in main.js. Releases contain only Obsidian's three supported assets.

The private CI builds the exact release tag. Artifact provenance availability depends on GitHub plan support for the private source repository; Obsidian's private-source build verification remains separate. Advisory typing, popout-window and CSS compatibility warnings are tracked; no claim is made that all warnings are resolved.

## Support and licenses

Report issues here without tokens, invitations, private notes or credentials. Client distribution is MIT licensed; see LICENSE and the embedded notices in main.js.

