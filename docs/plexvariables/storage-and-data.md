# PlexVariables Storage and Data

PlexVariables uses local SQLite storage for persistent stored variables.

## Scopes

### Player

Player-scoped stored values belong to an individual player.

### Global

Global stored values are shared server-wide.

Global aliases can be resolved with:

```text
%plexvar_global_<id>%
```

## Runtime Model

Persistent data is loaded into memory for normal placeholder resolution.

Database work is handled asynchronously so normal placeholder lookups do not perform database I/O directly.

## Operational Guidance

Back up the PlexVariables plugin data directory before manually modifying or replacing persistent data.

Avoid editing the SQLite database while the server is actively using it.

## Compatibility

Storage compatibility and migration behavior should be checked in the changelog before upgrading across versions that alter persistence internals.
