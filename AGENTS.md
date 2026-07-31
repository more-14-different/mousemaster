# Repository Guidelines

## Project Structure & Module Organization

Production code lives in `src/main/java/mousemaster`. Core input, mode, grid, and hint logic stays in the base package; platform-specific Windows integrations belong in `mousemaster.platform.windows`, and Qt overlay code belongs in `mousemaster.qt`. Runtime resources, native-image metadata, Qt binaries, and application properties are under `src/main/resources`. JUnit tests mirror the main package in `src/test/java/mousemaster`. User-facing presets and their documentation live in `configuration/`; keep a preset's `.properties` file and matching `.md` guide synchronized. `pefrmdllembed/` contains release-packaging binaries, not application source.

## Build, Test, and Development Commands

Use the checked-in Maven wrapper from PowerShell:

- `.\mvnw.cmd test` compiles the project and runs all JUnit tests.
- `.\mvnw.cmd clean package` creates the regular JAR and the dependency-bundled JAR in `target/`.
- `.\mvnw.cmd -Pnative package` builds `target/mousemaster.exe`; this requires GraalVM for Java 21.
- `java -jar target\mousemaster-*-jar-with-dependencies.jar --configuration-file=configuration\author.properties` runs a packaged JVM build with a sample configuration.

The application targets Windows; native builds and overlay/input behavior should be verified on Windows.

## Coding Style & Naming Conventions

Follow the existing Java style: four-space indentation, opening braces on the declaration line, one public top-level type per file, and imports grouped with `java.*` after third-party/project imports. Use `PascalCase` for types, `camelCase` for methods and variables, and `UPPER_SNAKE_CASE` for enum constants. Prefer focused records and enums where they model immutable values. No formatter or lint plugin is configured, so keep changes consistent with neighboring code and avoid unrelated reformatting.

## Testing Guidelines

Tests use JUnit Jupiter 5. Name test classes `*Test` and test methods after the scenario and outcome, such as `emptySequence_returnsComplete`. Add regression tests for parser, combo, and state-transition changes. Run `.\mvnw.cmd test` before submitting. The project has no declared coverage threshold; prioritize behavioral edge cases over percentage targets.

## Commit & Pull Request Guidelines

Recent commits use short, imperative summaries such as `Rename MouseController to MouseManager` and `Clean up`. Keep each commit focused and explain non-obvious behavior in the body. Pull requests should describe the user-visible impact, implementation approach, and test commands run; link relevant issues. Include screenshots or short recordings for Qt overlay, hint styling, or cursor changes, and note any configuration compatibility or native-image metadata updates.
