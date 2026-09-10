# notpritam’s BB Extensions

Add this marketplace once to browse and install my public extensions inside [BB](https://getbb.app).

## Add the marketplace

Run this on the machine running BB:

```sh
bb marketplace add git:github.com/notpritam/bb-marketplace@main
```

Open **Extensions**, search for **Guided Review** (or another plugin below), and choose **Install**. Review BB’s source confirmation. Adding a marketplace installs no plugins by itself.

You can also search and install from a terminal:

```sh
bb plugin search "Needs You"
bb plugin install inbox@notpritam
```

## Available extensions

| Extension | Install ID | What it does |
| --- | --- | --- |
| [Guided Review](https://notpritam.in/plugins/guided-review) | `guided-review@notpritam` | Chaptered PR walkthroughs, diffs, private notes, and an assistant; manual or optional idle updates |
| [Needs You](https://notpritam.in/plugins/needs-you) | `inbox@notpritam` | Questions, failed runs, and finished work in one inbox; optional Telegram notifications |
| [Transparency](https://notpritam.in/plugins/transparency) | `glass@notpritam` | Translucent surfaces, six animated backdrops, and a custom GLSL shader studio |

Guided Review requires BB 0.41+, Node 24+, GitHub CLI, Git, and a configured BB agent. Each reviewer signs in to GitHub on their own BB server. Open Guided Review → Settings to check setup and update preferences. No token is entered in the plugin. With Needs You 0.2.0-beta.3+ installed, guide completion and failure alerts open the review directly.

Needs You requires BB 0.41+ with Node 24+ on its host. Its inbox needs no credentials or Atlas. Optional Telegram setup is guided inside Needs You → Settings; phone replies and approvals remain inside BB. Settings also includes notification preferences and explicit update controls. See the [setup guide](https://github.com/notpritam/bb-plugin-inbox#optional-telegram-notifications).

Transparency requires BB 0.41+. Open **Transparency** in the sidebar or Settings and turn on **Enable transparency**. No account, API key, or subscription is needed. Appearance starts disabled; compact screens keep reading surfaces opaque. Custom shaders can be imported, previewed, saved, and exported. See the [setup and shader guide](https://github.com/notpritam/bb-plugin-glass#install-and-enable).

## New extensions and updates

New entries appear after BB refreshes the catalog. To refresh immediately:

```sh
bb marketplace refresh notpritam
```

A refresh only updates the list and icons. You choose which plugins to install or update. For example:

```sh
bb plugin update inbox
```

The catalog selects released Git tags within each entry’s version range. Guided Review tracks `^0.2.1`; Needs You tracks `^0.2.0`; Transparency tracks `^0.2.0`. A normal code push does not release an update. Unlisted plugins do not appear automatically.

## Publishing another extension

1. Publish its public repository with the required build artifacts and a new immutable version tag.
2. Add its actual plugin ID, name, concise description, author, public source and compatible tag range to `marketplace.json`.
3. Copy its monochrome icon into `icons/` and reference it from the entry.
4. Validate the catalog with BB, then push the catalog change to `main`.

For an existing entry, publish a new matching version tag to make that release eligible for users’ next update. Change the catalog when its source, version range or listing changes. Keep private and unfinished extensions out of this public catalog.

The catalog stores metadata and icons. Plugin code stays in each extension’s repository. This is an independently maintained marketplace, separate from the reviewed BB Community catalog.
