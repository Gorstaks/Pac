# Pac

Browser-side ad and tracker blocking: a proxy auto-config file, a userscript, and a registry file that applies the PAC.

## Contents

| File | Purpose |
|------|---------|
| `BlockAds.pac` | Proxy auto-config file. Sends blacklisted hosts and URLs (including URLs containing `xss`) to a blackhole proxy at `127.0.0.1:3421`. Everything else goes `DIRECT`. Has a whitelist, an on/off toggle (`isEnabled`) and a debug flag. |
| `GSecurity.user.js` | Userscript (Tampermonkey or similar). Blocks ads, crypto miners, malicious scripts, trackers, fingerprinting and popups. |
| `Pac.reg` | Sets `AutoConfigURL` for the current user to the hosted `BlockAds.pac`. |

## Usage

**PAC file**

1. Double-click `Pac.reg` and accept the prompt. This points Windows at the hosted `BlockAds.pac`.
2. To use a local copy instead, edit the `AutoConfigURL` value to a `file:///` URL.
3. To undo, delete the `AutoConfigURL` value under `HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings`.

**Userscript**

Install a userscript manager and open `GSecurity.user.js` in it.

## Releases

`Releases/0.0.1/Pac-0.0.1.zip` contains all three files.

## License

The userscript is MIT licensed (see its header).
