# PlexVariables Installation

This page covers the basic installation and first-start process for PlexVariables.

## Requirements

| Requirement | Value |
| --- | --- |
| Server software | Paper |
| Minecraft | 1.21+ target |
| Java | 21 |
| PlaceholderAPI | Required |
| Runtime validation | Paper 1.21.11 |

## Install

1. Install PlaceholderAPI.
2. Place `PlexVariables-1.0.0.jar` in the server's `plugins/` directory.
3. Start or restart the server.
4. Confirm PlexVariables enables without errors.
5. Open `plugins/PlexVariables/variables/` and edit or add variable files.
6. Run `/pv reload` after supported configuration changes.

## Generated Data

PlexVariables uses its plugin data directory for configuration, variable definitions, messages, and persistent SQLite data.

Typical locations include:

```text
plugins/PlexVariables/config.yml
plugins/PlexVariables/messages.yml
plugins/PlexVariables/variables/
plugins/PlexVariables/data.db
```

## Placeholder Format

Standard PlexVariables placeholders use:

```text
%plexvar_<id>%
```

Global stored aliases can also use:

```text
%plexvar_global_<id>%
```

## First Verification

After installation, use a known configured variable with PlaceholderAPI or the PlexVariables parse command.

Example:

```text
/pv parse --null %plexvar_server_name%
```

If the variable is player-dependent, provide an online or cached player instead of `--null`.
