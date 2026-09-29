# Installing myOS

myOS is a single HTML file, so "installing" it just means getting that file onto your device and opening it fullscreen. Pick your platform below.

The file you need is **`index.html`** — download it from the [latest release](https://github.com/kurupdevs/my-os/releases/latest) or clone this repo.

---

## Android (easiest)

1. Download **myOS-v1.0.apk** from the [latest release](https://github.com/kurupdevs/my-os/releases/latest) on your phone.
2. Open the downloaded file. If Android asks, allow **"Install unknown apps"** for your browser/files app.
3. Tap **Install**. Done — you'll find **myOS** in your app drawer.

The app opens straight into the OS in fullscreen landscape. No internet needed except for browsing, radio and YouTube.

> To update later, just install the newer APK over the old one — your settings carry over.

---

## Windows

### Option 1 — just open it

1. Download `index.html` to anywhere (e.g. `Downloads`).
2. Double-click it. It opens in your default browser as a full desktop.

### Option 2 — fullscreen kiosk mode (feels like a real OS)

This hides the browser UI completely:

1. Find where Chrome is installed (usually `C:\Program Files\Google\Chrome\Application\chrome.exe`).
2. Open **Command Prompt** (`Win + R`, type `cmd`, Enter) and run:

```cmd
"C:\Program Files\Google\Chrome\Application\chrome.exe" --kiosk "file:///C:/Users/YOURNAME/Downloads/index.html"
```

Replace `YOURNAME` with your Windows username (and the path if you saved the file elsewhere). To exit kiosk mode, press `Alt + F4`.

> Tip: put that command in a `.bat` file on your desktop and you have a one-click myOS launcher.

### Option 3 — serve it on your local network

With Python installed, from the folder containing `index.html`:

```cmd
cd Downloads
python -m http.server 8080
```

Then open `http://localhost:8080/index.html` — or `http://YOUR-PC-IP:8080/index.html` from your phone on the same Wi-Fi.

---

## Linux

### Option 1 — just open it

```bash
xdg-open index.html
```

### Option 2 — fullscreen kiosk mode

```bash
chromium --kiosk file:///home/$USER/Downloads/index.html
# or with google-chrome:
google-chrome --kiosk file:///home/$USER/Downloads/index.html
```

Exit with `Alt + F4`.

### Option 3 — local server

```bash
cd ~/Downloads
python3 -m http.server 8080
```

Then visit `http://localhost:8080/index.html`.

---

## Notes

- **Offline:** everything except web browsing, radio, weather and YouTube search works without internet — the music, videos, wallpapers and apps are all embedded in the file.
- **Your data** (notes, files, settings, icon positions) is stored in the browser's local storage on that device.
- **Updates:** replace `index.html` with the newer version. Your data stays, since it's in the browser, not the file.
