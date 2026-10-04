# PlexVariables Commands and Permissions

This page lists the PlexVariables command aliases, subcommands, and permissions.

## Command Aliases

The main command is available as:

```text
/plexvariables
/plexvar
/pvar
/pv
```

## Commands

| Command | Purpose | Permission |
| --- | --- | --- |
| `/pv help` | Show command help | `plexvariables.use` |
| `/pv list [page]` | List loaded variables, types, and source files | `plexvariables.list` |
| `/pv reload` | Reload configuration and variable files transactionally | `plexvariables.reload` |
| `/pv parse <player\|--null> <text>` | Parse text containing placeholders | `plexvariables.parse` |
| `/pv test <player\|--null> <variable>` | Trace variable evaluation | `plexvariables.test` |
| `/pv set <variable> <player\|global> <value>` | Set a stored variable value | `plexvariables.set` |
| `/pv add <variable> <player\|global> <amount>` | Add to a stored variable value | `plexvariables.add` |
| `/pv get <variable> [player\|global]` | Read a stored and default value | `plexvariables.get` |
| `/pv reset <variable> <player\|global>` | Reset a stored value to its default | `plexvariables.reset` |

## Administrative Permission

`plexvariables.admin` grants the PlexVariables command sub-permissions.

All command permissions default to operator access in the bundled plugin metadata unless changed by the server's permission system.

## Player Context

Commands that accept `<player|--null>` can either resolve against a player context or explicitly run with no player context.

Use `--null` only for variables that do not require player-specific data.
