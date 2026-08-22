# Dice Chess Reference Bot — AI Agent Guidelines

## Architecture Overview
- **Domain**: Reference bot and starter kit for the Dice Chess Bot API (JVM / Scala 3).
- **Core Stack**: Cats Effect 3, FS2, http4s Ember client, Circe, Logback, Munit Cats Effect.
- **Engine**: Wraps `com.fortemate:dicechess-engine` for game rules, legality checking, and search algorithms (greedy, monte-carlo, aggressive, etc.).
- **Strategy**: Extensible `Strategy` interface (`chooseMoves(ctx: MoveContext): Option[List[String]]`).
- **Licensing**: MIT. (Note: linking `com.fortemate:dicechess-engine` subjects the combined distribution to AGPL-3.0 terms).

## Developer Workflows
- **Toolchain**: Managed via `mise` (`mise run setup`, `mise run check`).
- **Core Runner**: Use `sbt` for all development activities.
- **Tests**: `sbt test` (runs Munit Cats Effect test suite).
- **Coverage**: `sbt "clean; coverage; test; coverageReport"` (`mise run coverage`).
- **Code Formatting**: `sbt scalafmtCheckAll scalafmtSbtCheck` / `sbt scalafmtAll scalafmtSbt`.
- **Packaging / Staging**: `sbt stage` via sbt-native-packager.

## Branch & Issue Guidelines
- **Branches**: `<type>/<short-desc>` or `<type>/<id>-<short-desc>` (`feat/`, `fix/`, `bug/`, `task/`, `refactor/`, `chore/`, `docs/`, `ci/`, `test/`, `perf/`).
- **GitHub Issues**: Use native GitHub Issue Types (`Feature`, `Task`, `Bug`) rather than issue labels.
- **PR Description**: Reference closed issues with `Closes #ID`.
- **Commits & PRs**: English language only.
