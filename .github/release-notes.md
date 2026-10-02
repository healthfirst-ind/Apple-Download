## IndiaMart Automation Tool — macOS (Apple Silicon)

Download the `.dmg` below, drag **IndiaMart Automation Tool** into `/Applications`, then launch it.

**First launch (one time, expected):**
macOS will block the app because it is ad-hoc signed and not notarized with an Apple
Developer ID. Right-click the app in `/Applications` → **Open** → **Open** in the dialog.
It launches normally from then on. Do not open the DMG through a download manager or a
cloud drive's "open in place" link — those strip the quarantine flag.

**Licensing:** the app registers this Mac's hardware ID on first run. An administrator
must approve it in the admin dashboard before it will activate.

**Install note:** if macOS reports the app "is damaged", clear the quarantine flag:

```bash
sudo xattr -cr "/Applications/IndiaMart Automation Tool.app"
sudo codesign --force --deep --sign - "/Applications/IndiaMart Automation Tool.app"
```

---

<sub>Built automatically from `healthfirst-ind/Apple-Client` by `release-mac.yml`. The version number in the asset filename comes from the release tag.</sub>
