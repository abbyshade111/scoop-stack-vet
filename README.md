# Scoop for StackVet

[StackVet](https://github.com/abbyshade111/StackVet)'s `sv` checks an app, written in any language, against the
OWASP security standards, and says plainly what it checked and what it did not.

This repository lets [Scoop](https://scoop.sh) install `sv` on Windows. Scoop downloads the Windows program from
StackVet's GitHub Releases, checks it against the published checksum, and puts `sv` on your path. Nothing is
compiled on your computer.

In PowerShell:

```powershell
scoop bucket add stackvet https://github.com/abbyshade111/scoop-stack-vet
scoop install stackvet/sv
sv.exe --version
```

**In PowerShell, type `sv.exe`, not `sv`.** PowerShell already uses `sv` as a short name for one of its own commands
(`Set-Variable`), so plain `sv` there does nothing visible. In the older Command Prompt, plain `sv` works.

To update later: `scoop update sv`.

Each release's zip is signed where GitHub built it. To check it yourself, download the zip from the release page
and run `gh attestation verify <the zip> --repo abbyshade111/StackVet`.

The check in `.github/workflows/test.yml` installs `sv` this way on Windows and runs a real check with it, on every
change here and once a week.
