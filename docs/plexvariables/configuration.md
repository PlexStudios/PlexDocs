# PlexVariables Configuration

This page documents the main PlexVariables runtime settings in `plugins/PlexVariables/config.yml`.

## Settings

| Setting | Default | Description |
| --- | ---: | --- |
| `max-resolution-depth` | `10` | Maximum nested PlexVariables resolution depth |
| `max-expansions` | `1000` | Total expansion work budget per parse request |
| `max-output-length` | `65536` | Maximum output character length |
| `warning-cooldown-seconds` | `60` | Cooldown before repeating identical resolution warnings |
| `list-page-size` | `10` | Entries shown per `/pv list` page |
| `error-value` | `""` | Fallback returned when guarded resolution fails |
| `colorize-placeholder-output` | `true` | Convert supported legacy and hex color formats |
| `conditions.case-sensitive` | `false` | Controls string-condition case sensitivity |
| `expressions.max-length` | `4096` | Maximum expression length |
| `expressions.max-tokens` | `512` | Maximum parsed expression token count |
| `expressions.max-parenthesis-depth` | `64` | Maximum expression parenthesis nesting depth |
| `storage.max-value-length` | `4096` | Maximum stored value length |
| `storage.shutdown-timeout-seconds` | `10` | Maximum shutdown wait for queued persistence work |

## Reload Behavior

`/pv reload` loads candidate configuration and variable state before publishing it.

If a fatal reload error occurs, the previous working state remains active instead of being replaced by a partially loaded state.

## Variable Files

PlexVariables recursively discovers `.yml` files below:

```text
plugins/PlexVariables/variables/
```

Subfolders are supported.

## Messages

Player-facing command messages are configured in:

```text
plugins/PlexVariables/messages.yml
```

Messages support the color formats documented by the plugin and use `%prefix%` only where the individual message includes it.
