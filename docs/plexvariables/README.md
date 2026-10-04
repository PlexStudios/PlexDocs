# PlexVariables

PlexVariables is a configurable PlaceholderAPI variable engine for Paper servers.

It allows server owners to define reusable variables in YAML and expose them through PlaceholderAPI without writing a custom plugin for every value.

## Requirements

| Requirement | Value |
| --- | --- |
| Server software | Paper |
| Minecraft | 1.21+ target |
| Java | 21 |
| PlaceholderAPI | Required |
| Runtime validation | Paper 1.21.11 |

## Placeholder Format

Standard variables:

```text
%plexvar_<id>%
```

Global stored aliases:

```text
%plexvar_global_<id>%
```

## Documentation

- [Installation](installation.md)
- [Variable Types](variable-types.md)
- [Commands and Permissions](commands-and-permissions.md)
- [Configuration](configuration.md)
- [Examples](examples.md)
- [Storage and Data](storage-and-data.md)
- [Troubleshooting](troubleshooting.md)

## Variable Types

PlexVariables currently supports:

- `STATIC`
- `CONDITIONAL`
- `EXPRESSION`
- `STORED`

Variables can reference other PlexVariables values, allowing larger systems to be composed from smaller definitions.

## Storage

Stored variables support player-scoped and global values backed by local SQLite storage.

Normal placeholder resolution uses cached values rather than performing database I/O on the hot path.

## Project Links

- [Repository](https://github.com/PlexStudios/PlexVariables)
- [Issues](https://github.com/PlexStudios/PlexVariables/issues)
- [GitHub Wiki](https://github.com/PlexStudios/PlexVariables/wiki)
