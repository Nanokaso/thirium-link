# Thirium Link

**English** · [Português](README.pt-BR.md)

Thirium Link is a small free Windows app that sends your PC's hardware info (CPU, GPU, memory, disk, network and
temperatures) to the **Thirium OS (Detroit: Become Human)** wallpaper for Wallpaper Engine.

Wallpapers can't read your hardware on their own. Without Thirium Link, everything else in Thirium OS still works;
only the hardware widget stays hidden.

## Download and install

1. Download **`ThiriumLink.exe`** from the [latest release](https://github.com/Nanokaso/thirium-link/releases/latest).
2. Open it once. That's it: it installs itself, starts with Windows and lives as an icon near the clock.

> **"Windows protected your PC"?** Windows shows this for apps without a paid code-signing certificate.
> Click **More info → Run anyway**. You can confirm the file is the official one with its SHA-256 hash
> (see [Check the file](#check-the-file)).

No .NET or anything else to install: everything is inside the .exe (about 52 MB).

## Using it

Click the icon near the clock:

| Option | What it does |
|--------|--------------|
| **Turn on CPU temperature...** | Optional. See below. |
| **Start with Windows** | On by default. |
| **View data** | Opens the data Thirium Link is sending, in your browser. |
| **Uninstall...** | Removes Thirium Link. Also available in Settings → Apps. |
| **Exit** | Closes it until the next time Windows starts. |

### CPU temperature (optional)

Windows only allows reading the CPU temperature through a kernel driver. Thirium Link uses **PawnIO**, a free and
signed driver (the same one LibreHardwareMonitor uses). When you choose *Turn on CPU temperature*:

1. Windows asks for confirmation **once**;
2. the official PawnIO installer runs (it's inside the .exe; no download needed);
3. Thirium Link starts as administrator with Windows from then on, without asking again.

Everything else (GPU temperature, usage, memory, disk, network) works without this.

## Is it safe?

- **Only on your PC:** nothing on your network or the internet can connect to it.
- **Read-only:** it can't change, run or delete anything on your PC.
- **No personal data:** it only shares hardware numbers.

## Check the file

Each release lists the SHA-256 hash of `ThiriumLink.exe`. To check yours, open PowerShell in the download folder and run:

```powershell
Get-FileHash .\ThiriumLink.exe -Algorithm SHA256
```

The result must match the hash in the release. **Only download Thirium Link from this page.**

## Problems?

- Hardware widget not showing: make sure the Thirium Link icon is near the clock. If it is, open
  `http://127.0.0.1:4580/diagnostico` in your browser and include what it shows when you report the problem.
- Report problems in [Issues](https://github.com/Nanokaso/thirium-link/issues).
- Found a security problem? Please **don't** open a public issue; see [SECURITY.md](SECURITY.md).

## Credits

Thirium Link uses [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor) and the
[PawnIO](https://pawnio.eu) driver. See [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

Fan-made project. Detroit: Become Human is a trademark of Quantic Dream. Not affiliated with Quantic Dream or Wallpaper Engine.
