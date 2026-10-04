# PlexVariables Examples

This page provides focused examples for the main PlexVariables variable types.

## Static

```yaml
variables:
  server_name:
    type: static
    value: "&d&lPlex Network"
```

Resolve with:

```text
%plexvar_server_name%
```

## Conditional

```yaml
variables:
  health_status:
    type: conditional
    conditions:
      - condition: "%player_health% <= 5"
        value: "&cCritical"
      - condition: "%player_health% <= 10"
        value: "&eLow"
    default: "&aHealthy"
```

Conditions are evaluated from top to bottom and the first matching branch wins.

## Expression

```yaml
variables:
  kd_ratio:
    type: expression
    expression: "%statistic_player_kills% / %statistic_deaths%"
    decimals: 2
    strip-trailing-zeros: true
    rounding-mode: HALF_UP
    on-error: "0"
```

Expression evaluation uses the plugin's safe mathematical expression engine.

## Stored Player Variable

```yaml
variables:
  player_gems:
    type: stored
    scope: player
    default: "0"
```

The effective value is available as:

```text
%plexvar_player_gems%
```

## Stored Global Variable

```yaml
variables:
  server_event_status:
    type: stored
    scope: global
    default: "inactive"
```

Resolve using either the normal variable identifier or the explicit global alias:

```text
%plexvar_server_event_status%
%plexvar_global_server_event_status%
```

## Composition

PlexVariables values can reference other PlexVariables placeholders.

Keep reusable pieces small and compose them into higher-level output where it improves readability.
