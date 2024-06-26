**IMPORTANT NOTE: We're starting to migrate contents of this repo to the [devcontainers org](https://github.com/devcontainers), as part of the work on the [open dev container specification](https://containers.dev).**

**We've currently migrated the `github-cli` Feature to [devcontainers/features/src/github-cli](https://github.com/devcontainers/features/tree/main/src/github-cli).**

**For more details, you can review the [announcement issue](https://github.com/microsoft/vscode-dev-containers/issues/1589).**

# GitHub CLI Install Script

*Installs the GitHub CLI. Auto-detects latest version and installs needed dependencies.*

**Script status**: Stable

**OS support**: Debian 9+, Ubuntu 18.04+, and downstream distros.

**Maintainer:** The VS Code and GitHub Codespaces teams

## Syntax

```text
./github-debian.sh [Version]
```

Or as a feature:

```json
"features": {
    "github-cli": "latest"
}
```

|Argument|Feature option|Default|Description|
|--------|--------------|-------|-----------|
|Version|`version`| `latest` | Version of GitHub CLI to install. Use `latest` to install the latest released version. Partial version numbers are allowed. |

## Usage

### Feature use

To install these capabilities in your primary dev container, reference it in `devcontainer.json` as follows:

```json
"features": {
    "github-cli": "latest"
}
```

If you have already built your development container, run the **Rebuild Container** command from the command palette (<kbd>Ctrl/Cmd</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> or <kbd>F1</kbd>) to pick up the change.

### Script use

1. Add [`github-debian.sh`](../github-debian.sh) to `.devcontainer/library-scripts`

2. Add the following to your `.devcontainer/Dockerfile`:

    ```Dockerfile
    COPY library-scripts/github-debian.sh /tmp/library-scripts/
    RUN apt-get update && bash /tmp/library-scripts/github-debian.sh
    ```

That's it!
