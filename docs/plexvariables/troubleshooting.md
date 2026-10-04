# PlexVariables Troubleshooting

This page covers common checks for PlexVariables problems.

## Placeholder stays unchanged

Check that:

1. PlaceholderAPI is installed and enabled.
2. PlexVariables is enabled.
3. The variable ID exists.
4. The placeholder uses `%plexvar_<id>%`.
5. The variable definition loaded successfully.
6. Player-dependent variables are being resolved with a valid player context.

Use:

```text
/pv list
/pv test <player|--null> <variable>
```

to inspect loaded variables and evaluation behavior.

## Reload fails

PlexVariables reloads configuration transactionally.

If `/pv reload` fails, the previous working state remains active.

Check the console for the configuration or YAML error, correct the file, then reload again.

## Conditional output is unexpected

Use:

```text
/pv test <player|--null> <variable>
```

Review the resolved operands and the branch selected by the condition engine.

Remember that conditional branches are checked from top to bottom.

## Expression returns its fallback

Check:

- placeholder inputs resolve to numeric values
- division or modulo is not using zero
- the expression is within configured work limits
- parentheses and function arguments are valid

Use `/pv test` to inspect the resolved expression and error information.

## Stored value does not appear

Check that:

- the variable type is `stored`
- the configured scope matches the command target
- a player-scoped value is resolved with the intended player
- the stored operation completed successfully
- the server is not currently shutting down

## Cyclic references

PlexVariables detects recursive variable cycles and stops resolution.

Break the reference chain so the variables no longer eventually reference themselves.

## Data Safety

Do not manually edit `data.db` while the server is actively using it.

Back up the PlexVariables data directory before replacing or manually modifying persistent data.
