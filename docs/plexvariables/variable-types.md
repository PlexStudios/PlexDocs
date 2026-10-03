# PlexVariables Variable Types

This page summarizes the four core PlexVariables variable types.

## STATIC

`STATIC` variables provide reusable values.

They are useful when a value should be defined once and referenced in multiple places.

## CONDITIONAL

`CONDITIONAL` variables select output using configurable conditions.

Use them when a placeholder should change based on another value or server/player state exposed to the variable engine.

## EXPRESSION

`EXPRESSION` variables evaluate mathematical expressions through the plugin's safe expression engine.

They are intended for calculations without arbitrary code execution.

## STORED

`STORED` variables persist values.

Supported scopes include:

- player
- global

Player values are associated with an individual player.

Global values are shared server-wide.

## Composition

Variables can reference other PlexVariables values.

This makes it possible to build larger systems from small reusable definitions.

PlexVariables includes cycle protection so invalid recursive chains do not resolve indefinitely.
