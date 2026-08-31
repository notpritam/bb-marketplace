# notpritam's BB Extensions — marketplace

A [BB](https://getbb.app) marketplace catalog for my personal plugins.

## Add it

```sh
bb marketplace add git:github.com/notpritam/bb-marketplace@main
# then, e.g.
bb plugin install ask-pro@notpritam
```

Locally from a checkout:

```sh
bb marketplace add path:/home/pritam/personal/extensions/bb-marketplace
```

## Catalog

| Plugin | id | What it does |
|---|---|---|
| Ask Pro | `ask-pro` | Advanced ask-the-user form — per-option context + a closing note |
| Atlas | `tracker` | Tasks, notes, and an activity graph |
| Transparency | `glass` | Glassy, translucent look for the whole app |
| MCP & Skills | `mcp-manager` | Manage Claude Code MCP servers and skills across machines |
| Tally | `tally` | Personal-finance tracker |

Each entry installs from its own public `notpritam/bb-plugin-*` repo, pinned to a
`^0.1.0` semver range so a new tagged release reaches users without editing this
catalog. Plugins with a private dependency (e.g. Mailroom, Account Switcher) are
intentionally not listed until they can be made public.

`marketplace.json` is the whole catalog; `icons/` holds one monochrome SVG per
entry. Never hosts plugin code — installing an entry runs BB's normal install
pipeline against the plugin's own repo.
