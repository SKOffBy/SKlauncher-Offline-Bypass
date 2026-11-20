# SKlauncher-Offline-Bypass

A tiny web page that creates a **SKlauncher accounts file** for you, so you can play offline
without signing in. Pick your launcher version, type a username, download the file, drop it in the
right folder. That's it.

Everything happens on your own device — nothing is uploaded anywhere.

> **Unofficial, community-made tool.** Not affiliated with, endorsed by, or associated with
> SKlauncher, Mojang Studios or Microsoft. Minecraft is a trademark of Mojang Studios.

## How to use it

1. Open the page (or double-click `index.html` to use it offline).
2. Choose your launcher: **SKlauncher 3.2** or **SKlauncher 4.0**.
3. Type your offline username (3–16 characters).
4. Click **Download**.
5. Close SKlauncher, put the downloaded file in the folder below, and open SKlauncher again.

## Where to put the file

**SKlauncher 3.2** → `accounts.bin`

| System | Folder |
|--------|--------|
| Windows | `%APPDATA%\.minecraft\sklauncher` |
| Linux | `~/.minecraft/sklauncher` |
| macOS | `~/Library/Application Support/minecraft/sklauncher` |

**SKlauncher 4.0** → `accounts.json`

| System | Folder |
|--------|--------|
| Windows | `%APPDATA%\.sklauncher` |
| Linux | `~/.sklauncher` |
| macOS | `~/Library/Application Support/sklauncher` |

Just paste the path into your file explorer's address bar to jump straight there.

## If the page ever stops working

Here's what the files look like, so you have a reference. **Notch** is included on purpose — leave
it as it is.

### SKlauncher 3.2 — `accounts.bin`

3.2 normally uses a packed file, which is why the tool builds it for you. But here's the easy
part: if you save the text below as **`accounts.json`** inside the 3.2 folder, the launcher
converts it into `accounts.bin` by itself the next time you open it. So even without the tool,
this works:

> **Important:** delete any existing `accounts.bin` in that folder first. SKlauncher only reads
> `accounts.json` when there is no `accounts.bin` — if the `.bin` is there, it uses that and
> ignores your `.json`.

```json
{
  "accounts": {
    "c5a1ed3367a83411bd0e04520683d321": {
      "displayName": "Example",
      "type": "msa",
      "uuid": "c5a1ed3367a83411bd0e04520683d321"
    },
    "069a79f444e94726a5befca90e38aaf5": {
      "displayName": "Notch",
      "type": "msa",
      "uuid": "069a79f444e94726a5befca90e38aaf5",
      "refreshToken": ""
    }
  },
  "activeAccountLocalId": "c5a1ed3367a83411bd0e04520683d321"
}
```

### SKlauncher 4.0 — `accounts.json`

This one is a plain text file: you can copy this, change the name, and save it as `accounts.json`.

```json
{
  "accounts": [
    {
      "id": "0c562367-853a-4bbe-9e87-aab488bd30df",
      "type": "offline",
      "username": "Example",
      "uuid": "c5a1ed33-67a8-3411-bd0e-04520683d321"
    },
    {
      "id": "e7c2c3d1-c200-46df-9caf-57addeff75e5",
      "type": "microsoft",
      "username": "Notch",
      "uuid": "069a79f444e94726a5befca90e38aaf5",
      "expiresAt": 0,
      "msaExpiresAt": 0,
      "lastRefreshAt": 0,
      "profile": {
        "uuid": "069a79f444e94726a5befca90e38aaf5",
        "username": "Notch",
        "skin": { "url": "", "variant": "classic" }
      }
    }
  ],
  "activeAccountId": "0c562367-853a-4bbe-9e87-aab488bd30df"
}
```

- `username` is your offline name.
- `uuid` is the offline UUID for that name. Each name has its own — you can get it from any
  "Minecraft offline UUID" website, or just read it off this tool.
- `id` is any random ID; the one above works fine, or use your own.

## Good to know

- You **can't play online** with the **Notch** account — but don't remove it. The launcher only
  lets you create offline users when a Microsoft account exists, so Notch is what keeps the
  "add offline account" option available. It doesn't affect your offline accounts otherwise.
- Nothing you type ever leaves your browser. No accounts, no tracking, no uploads.
