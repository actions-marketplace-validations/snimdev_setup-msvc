# setup-msvc

Sets up the MSVC developer environment (the equivalent of a Developer Command Prompt) for the rest of a GitHub Actions job on Windows. A composite action in PowerShell, so it needs no Node.js runtime.

It finds the latest Visual Studio or Build Tools with the C++ x64 tools through `vswhere`, runs `vcvarsall.bat`, and exports the changed variables: new `PATH` entries through `GITHUB_PATH` in vcvars' order, everything else through `GITHUB_ENV`.

```yaml
- uses: snimdev/setup-msvc@v1
  with:
    arch: x64  # any vcvarsall.bat argument: x64, x86, amd64_arm64, ...
```

Requires PowerShell 7 (`pwsh`) on the runner, which GitHub-hosted Windows images include.
