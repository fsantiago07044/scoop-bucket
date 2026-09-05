# FSP Productions Scoop Bucket

A [Scoop](https://scoop.sh) bucket for software published by FSP Productions, LLC.

## Install

```powershell
scoop bucket add fsantiago https://github.com/fsantiago07044/scoop-bucket
scoop install filehasher
```

If you don't have Scoop yet:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

## What's in it

| App | Description |
| --- | --- |
| [filehasher](bucket/filehasher.json) | Hash files and folders, write and verify sidecar hash files, and export results to CSV. |

## Notes

Scoop installs the **portable** build: it unpacks into your Scoop apps
directory and adds a Start Menu shortcut. Nothing goes into Program Files,
nothing appears in Add/Remove Programs, and no administrator rights are needed.
`scoop uninstall filehasher` removes it cleanly. Logs the app writes to
`%AppData%\FileHasher\Logs` are outside the Scoop directory and are left alone
by install, update and uninstall.

Every download is checked against the SHA-256 published alongside the release,
and the executable inside is Authenticode-signed by FSP Productions, LLC.

Manifests here update themselves: a scheduled
[Excavator](.github/workflows/excavator.yml) run checks for new releases and
commits the new version and checksum, so `scoop update` picks up a release
without anyone touching this repo.

## Other ways to install

FileHasher is also on [winget](https://github.com/microsoft/winget-pkgs)
(`winget install FSPProductions.FileHasher`), and the signed installer and
portable builds are on the
[releases page](https://github.com/fsantiago07044/filehasher/releases/latest).
