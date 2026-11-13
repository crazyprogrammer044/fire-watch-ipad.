FIRE WATCH — iPad Pro M4 FRONT-CAMERA WEB APP
================================================

WHAT THIS IS
------------
A browser-based student demo. It requests the iPad front camera, displays a
mirrored preview, checks sampled pixels for red/orange/yellow colour patterns,
and plays an alarm when the threshold is exceeded. You can choose your own
audio file, such as the "Aaaaaaagggg!!" voice.

IMPORTANT LIMITATION
--------------------
This is a colour heuristic, NOT an AI fire model. It can trigger on orange
objects/lights and miss real fire. Do not use it as a real fire alarm.

WHY HTTPS IS REQUIRED
---------------------
iPad Safari only allows camera access to secure pages (HTTPS) or localhost.
Opening index.html directly from Files will generally NOT allow camera access.
To install it like an app, host these files on an HTTPS static site.

EASIEST DEPLOYMENT: GITHUB PAGES
--------------------------------
1. On a computer, sign in/create a GitHub account.
2. Create a NEW public repository named: fire-watch-ipad
3. Upload all six files from this folder into the repository root:
   index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png
   (plus this README if you want).
4. In repository Settings -> Pages:
   - Source: Deploy from a branch
   - Branch: main
   - Folder: / (root)
   - Save.
5. Wait for GitHub Pages to publish. Your URL will look like:
   https://YOUR-USERNAME.github.io/fire-watch-ipad/
6. On iPad Pro M4, open that HTTPS URL in Safari.
7. Tap Share -> Add to Home Screen.
8. Enable "Open as Web App" if shown, then tap Add.
9. Launch Fire Watch from the Home Screen.
10. Tap Start Camera and allow camera permission. It asks for the front
    camera (facingMode user). If iPadOS shows a camera chooser, select Front.

CUSTOM ALARM
------------
Inside Fire Watch, tap "Choose alarm voice" and select an audio file supported
by iPadOS/Safari (MP3, M4A, WAV, etc.) from Files. Tap Test Alarm once.
The selected file is held in the current page session; reselect it after a
full app reload if needed.

TESTING
-------
- First tap Test Alarm to verify sound.
- Tap Start Camera and accept permission.
- Test with a safe fire video displayed on another screen, not a real flame.
- Bright orange/yellow objects may create false alerts.
- Keep the app in the foreground; iPadOS may suspend camera processing when
  the app is backgrounded or the screen locks.

TROUBLESHOOTING
---------------
Camera permission: iPad Settings -> Safari -> Camera, or website settings
from Safari address bar, then allow camera. Exact menu wording can vary.
If no camera: close FaceTime/other camera apps and reload the HTTPS page.
If Home Screen app does not update: close it fully, reopen; if needed remove
the Home Screen icon and add it again after clearing website data/cache.

NO PAID SOFTWARE OR PYTHON REQUIRED
-----------------------------------
The app uses HTML, CSS and JavaScript. Hosting on GitHub Pages can be free.
