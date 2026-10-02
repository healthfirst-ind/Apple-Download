## IndiaMart Automation Tool — macOS (Apple Silicon)

Download the `.dmg` below, drag **IndiaMart Automation Tool** into `/Applications`, then launch it.

**First launch (one time, expected):**
macOS will block the app because it is ad-hoc signed and not notarized with an Apple
Developer ID. On macOS 15 (Sequoia) and 26 (Tahoe), Apple removed the right-click → Open
shortcut, so approval happens in System Settings instead:

1. Double-click the app. When it says *"Apple could not verify … is free of malware"*,
   click **Done** (not "Move to Bin").
2.  → **System Settings** → **Privacy & Security**.
3. Scroll to **Security** — it will say the app was blocked. Click **Open**.
4. Confirm **Open Anyway** and enter your Mac password.

It launches normally from then on. If "Open Anyway" is missing, double-click the app once
more to re-trigger the warning, then return to Privacy & Security.

**Terminal alternative (one line, skips all of the above):**

```bash
sudo xattr -cr "/Applications/IndiaMart Automation Tool.app"
```

**Licensing:** the app registers this Mac's hardware ID on first run. An administrator
must approve it in the admin dashboard before it will activate.

**Install note:** if macOS reports the app *"is damaged"*, the bundle is unsigned — that
only happens on builds made before the ad-hoc signing fix. Rebuild, or recover with:

```bash
sudo xattr -cr "/Applications/IndiaMart Automation Tool.app"
sudo codesign --force --deep --sign - "/Applications/IndiaMart Automation Tool.app"
```

---

<sub>Built automatically from `healthfirst-ind/Apple-Client` by `release-mac.yml`. The version number in the asset filename comes from the release tag.</sub>
