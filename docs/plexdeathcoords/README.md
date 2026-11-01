# PlexDeathCoords

PlexDeathCoords is a lightweight Paper plugin by Plex Studios that records the **most recent death location** for each player. It stores world identity, coordinates and the time of death, so players can find their way back after respawning.

**Source and full reference:** [PlexStudios/PlexDeathCoords](https://github.com/PlexStudios/PlexDeathCoords)

## Requirements

- **Server:** Paper for Minecraft 1.21 or newer (not Spigot, Bukkit or Folia).
- **Java:** The plugin targets Java 21. The *server* must run on the Java version required by its Paper build (Java 25 for Paper 26.1+).
- **Dependencies:** No additional plugins required.
- **Current documented plugin version:** 1.1.0.

Compatibility with every individual server version has not been verified. Check the [source README](https://github.com/PlexStudios/PlexDeathCoords#requirements) for the latest compatibility notes.

## Installation

1. Obtain the official plugin JAR or build the project from source using its included Gradle wrapper.
2. Stop the Paper server, put the JAR in the `plugins/` directory and start the server.
3. Configure `plugins/PlexDeathCoords/config.yml` as needed.
4. Use `/plexdeathcoords reload` after subsequent configuration edits.

The plugin only records deaths that happen while it is enabled. It does not import historical death locations from vanilla Minecraft.

## Commands and permissions

| Command | Purpose | Permissions |
| --- | --- | --- |
| `/lastdeath` or `/deathcoords` | Show your saved death location | `plexdeathcoords.use` |
| `/lastdeath clear` | Clear your saved death | `plexdeathcoords.use`, `plexdeathcoords.clear` |
| `/lastdeath compass` | Point a regular held compass to the saved death in the same world | `plexdeathcoords.use`, `plexdeathcoords.compass` |
| `/plexdeathcoords reload` | Reload the configuration | `plexdeathcoords.admin` |

The `clear` and `compass` subcommands also work under `/deathcoords`. Viewing, clearing and compass targeting are player-only. Reload is available to administrators and the console. Permission defaults and additional details are in the [source README](https://github.com/PlexStudios/PlexDeathCoords#commands-and-permissions).

## Common configuration

```yaml
coordinate-precision: 0
show-world: true
show-time: true
allow-clear: true
clickable-coordinates: true
respawn-reminder: false
allow-compass: true
```

The plugin supports MiniMessage-formatted text, clickable coordinates that copy to the clipboard, an optional post-respawn reminder, and command feedback customization. For all supported settings and message placeholders, use the [complete configuration guide in the source repository](https://github.com/PlexStudios/PlexDeathCoords#configuration).

## Storage and backups

- The latest death is stored per player UUID in `plugins/PlexDeathCoords/deaths.yml`.
- New deaths replace the previous saved location; this is **not a death-history plugin**.
- Storage writes happen in the background. Abnormal shutdowns or storage failures can prevent the newest data from being written.
- Back up the YAML file before changing it manually; stop the server before editing.

## Build, troubleshooting and support

Build with JDK 21 using `./gradlew clean build` (Linux/macOS) or `.\gradlew.bat clean build` (Windows). The build runs automated tests; consult the repository's [release notes](https://github.com/PlexStudios/PlexDeathCoords/blob/main/RELEASE_NOTES.md) for the tested scope and remaining limitations.

For installation, data, permissions and reload issues, consult the [troubleshooting section](https://github.com/PlexStudios/PlexDeathCoords#troubleshooting), then report reproducible problems via [GitHub Issues](https://github.com/PlexStudios/PlexDeathCoords/issues).
