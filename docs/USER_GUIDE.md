# Playlist to MP3: User Guide

Version 1.2 · Powered by **Sorasit (Joh)**

Playlist to MP3 is a Windows app that saves YouTube playlists and videos as MP3 files on your PC. It works quietly in the background, like OneDrive or Google Drive, and continues by itself after a restart or an internet drop.

---

## 1. Install

1. Download **`PlaylistToMP3_Setup_v1.2.exe`** from the [Releases page](https://github.com/Powerautomateshare/Playlist-To-MP3/releases/latest).
2. Double-click it.
   - If you see **"Windows protected your PC"**, click **More info**, then **Run anyway**.
   - If you see **"Smart App Control blocked an app"**, turn it off: open **Windows Security**, go to **App & browser control**, then **Smart App Control settings**, and choose **Off**. This happens because the app isn't signed with a paid certificate.
3. Click **Next** through the steps. You don't need an administrator password.
4. Leave **Open Playlist to MP3 now** ticked and click **Finish**.

The app installs to `%LOCALAPPDATA%\Programs\PlaylistToMP3`. It adds a Start menu entry, an optional desktop icon, and an entry in **Settings → Apps → Installed apps**.

---

## 2. The main window

| Area | What it does |
|---|---|
| **Top right button** | Shows your YouTube sign-in state. Click it to fix the sign-in. |
| **Gear icon** | Opens Settings. |
| **Search box** | Type a name to search, or paste one or more links. |
| **Add links** | Paste many links at once, one per line. |
| **My playlists / Playlists / Videos** | Chooses what to search. |
| **Results** | Search results. Each one has an **Add** button. |
| **Download list** | Everything waiting to download. The **X** removes one item. **Clear list** removes all of them. |
| **Folder + Browse** | Where new MP3 files are saved. |
| **Subfolder per playlist** | Gives each playlist its own folder. |
| **Progress** | For example "208 of 1249 done", plus a progress bar and a **Retry failed** button. |
| **Song list** | The songs of the selected list item and the status of each one. |
| **Start / Pause / Stop** | Controls downloading. |

---

## 3. Download a playlist

1. Add something to the **Download list** in any of these ways:
   - **Search:** type a name, choose the **Playlists** or **Videos** tab, press **Search**, then press **Add** on each result you want.
   - **Paste a link:** paste a playlist or video link into the search box and press **Enter**. You can paste several links separated by spaces.
   - **Many links:** click **Add links**, paste one link per line, then click **Add to list**.
   - **Your own playlists:** click **My playlists**. This needs sign-in (see section 5).
2. Click **Browse** to choose the folder for the MP3 files. The default is your *Music* folder.
3. Press **Start**.

The app downloads the list from top to bottom, one song at a time. Each file is named after its video, for example `Song title.mp3`. If two videos in one playlist have the same title, the video ID is added so neither file is overwritten.

**Song status:**

| Status | Meaning |
|---|---|
| Waiting | Not started yet. |
| 45% / Converting to MP3 | Downloading now. |
| Done | Saved. |
| Waiting (YouTube busy) | YouTube asked the app to slow down. It retries by itself. |
| Failed | Couldn't be downloaded. Hover or right-click to see why. |

---

## 4. Pause, stop, clear

- **Pause** stops after a moment. **Resume** continues the same song.
- **Stop** ends the run. Pressing **Start** later continues where it stopped.
- The **X** on a list item removes that item. **Clear list** removes everything and resets the progress.
- **Saved MP3 files are never deleted** by any of these buttons.

---

## 5. Sign in to YouTube (optional)

Public playlists download without signing in. Signing in lets you see **My playlists**, download private playlists you own, and get fewer "YouTube busy" waits.

Edge, Chrome and Brave **lock their sign-in** so that other apps can't read it. Use one of these two methods instead:

### Option A: Firefox (easiest)
1. Install Firefox and sign in to **youtube.com**.
2. In the app, open the gear icon, set **YouTube sign-in** to **Firefox**, and click **Check sign-in**.

### Option B: Microsoft Edge with a cookies.txt file
1. In Edge, open the add-ons store and install **Get cookies.txt LOCALLY**.
2. Go to **youtube.com** and make sure you're signed in.
3. Click the add-on's icon, then **Export**. A file such as `www.youtube.com_cookies.txt` is saved to Downloads.
4. **Drag that file onto the app window.** You can also open the gear icon, choose **cookies.txt file**, click **Browse**, and pick the file.
5. The top-right button changes to **Signed in via cookies.txt**.

> Keep the cookies.txt file private. It works like a password for your YouTube account.
> If YouTube asks you to sign in again later, export a new file the same way.

---

## 6. Background and automatic resume

- Closing or minimizing the window keeps the app running in the **taskbar tray**, next to the clock.
- **Double-click** the red tray icon to open the window. **Right-click** it for **Open window**, **Pause/Resume**, **About** and **Exit**.
- The app **starts with Windows**. About 20 seconds later it continues any unfinished list.
- **Internet drop:** it waits, then continues the same song.
- **YouTube busy:** it waits 10, then 20, then at most 30 minutes, with a countdown. Press **Try now** to retry right away, for example after switching to a phone hotspot.
- While downloading, it keeps Windows from going to sleep. The screen can still lock.
- Every hour it checks your playlists for **new videos** and downloads only those.
- Songs you already have are never downloaded again.

---

## 7. When something fails

1. Hover over a **Failed** song to see the reason. You can also right-click it and choose **Copy error message**.
2. Press **Retry N failed** to try all failed songs again.
3. Right-click menu options:
   - **Try this video again**
   - **Open on YouTube**
   - **Open saving folder**
   - **Open error log**

| Reason | What to do |
|---|---|
| Private video / Video unavailable / Members-only | Can't be downloaded. |
| Age-restricted | Sign in (section 5), then retry. |
| YouTube wants a sign-in / too many downloads | Wait for the countdown, sign in, or use another internet connection. |
| Downloads stop working after some weeks | YouTube changed something. Install the newest version from Releases. |

---

## 8. Settings (gear icon)

| Setting | Default |
|---|---|
| YouTube sign-in | Firefox if installed, otherwise none |
| MP3 quality | 192 kbps (choose from 128 to 320) |
| Start with Windows and continue | On |
| Check playlists for new videos every hour | On |

Where your data is stored: `%APPDATA%\PlaylistToMP3`

- `state.json`: download list, progress and settings
- `errors.log`: error details
- `app.log`, `crash.log`: technical logs

---

## 9. Update or uninstall

- **Update:** run the newer `PlaylistToMP3_Setup_vX.Y.exe`. It closes the app, updates it, and keeps your download list.
- **Uninstall:** go to **Settings → Apps → Installed apps → Playlist to MP3 → Uninstall**. This removes the app, its shortcuts and the auto-start entry. Your MP3 files are kept.

---

## 10. Fair use

Downloading from YouTube is against YouTube's terms of service. Please use this app only for content you have the right to keep, such as your own uploads or freely licensed content.
