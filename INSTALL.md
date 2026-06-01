# Wavmaster — Install

Wavmaster needs three free helper programs — **ffmpeg**, **sox**, and **mpv** — which do the audio
decoding, effects, and playback. Install those once, then run Wavmaster. Nothing else to set up:
Python and the interface are built into the app.

**Get Wavmaster:** download the zip for your OS from the [Releases page](https://github.com/IronWolve/wavmaster/releases) and unzip it —
- Windows → `Wavmaster_win_x86_64.zip`
- Linux (x86-64) → `Wavmaster_linux_x86_64.zip`

Each zip contains the app plus a demo song + reference track so you can try it right away.

---

## Windows

### 1. Install the tools (Scoop — recommended)

[Scoop](https://scoop.sh) installs all three onto your PATH so Wavmaster finds them automatically.
In **PowerShell**:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
scoop install git
scoop bucket add extras
scoop install ffmpeg mpv sox
```

`ffmpeg` is in Scoop's **main** bucket; `mpv` and `sox` are in **extras** (that's why you add it —
and `git` is needed to add buckets). When it finishes, **open a new terminal** so the PATH updates,
then verify: `where ffmpeg; where ffprobe; where mpv; where sox`

### 2. Run it

Unzip `Wavmaster_win_x86_64.zip` and double-click **`Wavmaster.exe`**. (First launch is a moment
slower while it unpacks.)

> **No Scoop?** Download the tools by hand and put them on your PATH, or drop `ffmpeg.exe`,
> `ffprobe.exe`, `sox.exe` (+ its DLLs), and `mpv.exe` into a **`tools\`** folder next to
> `Wavmaster.exe` (if that folder exists, Wavmaster uses it before the PATH):
>
> | Tool | Download |
> |---|---|
> | **ffmpeg** (+ ffprobe) | https://github.com/BtbN/FFmpeg-Builds/releases — the `…win64-lgpl.zip` |
> | **SoX** | https://sourceforge.net/projects/sox/files/sox/14.4.2/ — `sox-14.4.2-win32.zip` |
> | **mpv** | https://sourceforge.net/projects/mpv-player-windows/files/64bit/ — latest `64bit` (not `64bit-v3`) |
>
> mpv/ffmpeg archives may be `.7z` (extract with [7-Zip](https://www.7-zip.org/)); SoX is a `.zip`.

---

## Linux (x86-64)

### 1. Install the tools

Use your distro's package manager. On Debian/Ubuntu:

```bash
sudo apt install ffmpeg sox mpv
```

(Fedora: `sudo dnf install ffmpeg sox mpv` · Arch: `sudo pacman -S ffmpeg sox mpv`.)
Verify: `which ffmpeg ffprobe sox mpv`

### 2. Run it

Unzip `Wavmaster_linux_x86_64.zip`, then make it executable and launch:

```bash
chmod +x Wavmaster_linux_x86_64
./Wavmaster_linux_x86_64
```

Needs a graphical desktop (X11 or Wayland) with working OpenGL. On a machine with no GPU/driver
(or some minimal/VM setups) where the window won't open, force software rendering:

```bash
LIBGL_ALWAYS_SOFTWARE=1 ./Wavmaster_linux_x86_64
```
