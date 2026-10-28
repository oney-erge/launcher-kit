# launcher-kit

The launcher helpers shared by oney-erge projects, kept in one place with
[Copier](https://copier.readthedocs.io) so a fix reaches every project.

| File | Purpose |
|---|---|
| `scripts/install-utils.ps1` | Install log and lock, retries, disk-space check, and `Invoke-InstallNative`, which runs native tools without Windows PowerShell 5.1 turning their stderr output into a fatal error |
| `scripts/install-utils.sh` | The same helpers for `run.sh` and `run.command` |
| `scripts/test-launcher-helpers.ps1` | Checks the PowerShell helpers under the Windows PowerShell 5.1 that `run.bat` starts |

Each project keeps its own `run.bat`, `run.ps1`, `run.sh` and `run.command`,
which dot-source these helpers.

## Use

Add the helpers to a project (from its root):

```bash
uvx copier copy --defaults gh:oney-erge/launcher-kit .
```

Pull in a newer version later:

```bash
uvx copier update --defaults
```

Copier records the template version in `.copier-answers.launcher-kit.yml`.
Release a change here by committing it and pushing a new `vX.Y.Z` tag.
