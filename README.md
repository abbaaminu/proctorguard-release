# ProctorGuard - release downloads

**This repository holds built artifacts only.** It is written by the release
workflow of the private ProctorGuard repository: the application's source
code, database schema and signing material are not here and never will be.

## Install on an Android phone

1. Download the APK that matches the phone's CPU:
   - `apk/app-arm64-v8a-release.apk` - every modern phone (pick this if unsure)
   - `apk/app-armeabi-v7a-release.apk` - older 32-bit phones
   - `apk/app-x86_64-release.apk` - x86 emulators, a few tablets
2. Allow installing from the browser or the file manager when Android asks
   ("Install unknown apps" for that app).
3. Install it, then sign in with the account the school issued.

With `adb`, the newest build installs over an older one without losing data:

```sh
adb install -r apk/app-arm64-v8a-release.apk
```

## Verify a download

```sh
cd apk && sha256sum -c SHA256SUMS.txt
```

Every APK is signed with the ProctorGuard upload key. A build from anywhere
else - or one whose signature does not match an existing install - is not an
official build: uninstall it rather than trusting it. The key is not in this
repository.

## What is in here

| path | what it is |
| --- | --- |
| `apk/*-release.apk` | the student app, one APK per CPU architecture |
| `apk/SHA256SUMS.txt` | SHA-256 of each APK above |
| `latest.json` | version, build number, commit and checksums of this build |

The file names never change: this repository always carries the newest build
from the private repository's `main`. Older builds stay reachable through this
repository's Git history.

## This build

| | |
| --- | --- |
| version | 1.0.1 |
| build number | 9 |
| commit | 0bb1446 |
| tag | v1.0.1 |
| built | 2026-10-06T19:21:19Z |
