# Baby's First Tracker — Capacitor iOS shell build record

- Shell: `~/workspace/testflight-all-products-2026-11-16/shells/lasttime/`
- Date: 2026-11-16 · Local work only — no GitHub push, no server change, no iMac use.
- Recipe: estate All-Apps recipe (feedtosold.md) / template shell town-shell.

## Identity / surface

- Bundle ID (task): `com.buckthem.lasttime`
- Display name (task): `Baby's First Tracker`
- App surface: `https://buckthem.com/lasttime/app`
- Surface source: ~/workspace/baby-app-bone3-2026-11-15/STATUS.md (buckthem.com/lasttime, app at /lasttime/app; manifest start_url /lasttime/app confirmed live)
- Live verification (proxy http://127.0.0.1:18080): **303 (via proxy http://127.0.0.1:18080, 2026-11-16; redirect to sign-in, expected for signed-out app surface)**

## Read-backs (exact)

- pbxproj `PRODUCT_BUNDLE_IDENTIFIER` values found: ['com.buckthem.lasttime', 'com.buckthem.lasttime'] — Debug and Release both == `com.buckthem.lasttime`: **True**
- Info.plist `CFBundleDisplayName`: **Baby's First Tracker**
- capacitor.config.json parses: **True**; appId `com.buckthem.lasttime`, appName `Baby's First Tracker`, server.url `https://buckthem.com/lasttime/app`, backgroundColor `#ffffff`, ios.contentInset `always`, ios.preferredContentMode `mobile`, cleartext `False`
- Usage strings in Info.plist: none beyond Capacitor defaults
- Resolved versions (package-lock.json): {'@capacitor/core': '6.2.3', '@capacitor/cli': '6.2.3', '@capacitor/ios': '6.2.3', '@capacitor/share': '6.0.4', '@capacitor/push-notifications': '6.0.5'}
- AppIcon: `AppIcon-512@2x.png` 1024x1024 + Contents.json copied verbatim from town-shell (single-size universal 1024 format).

## Icon / splash

- Icon source: canonical — product lane dir ~/workspace/baby-app-bone3-2026-11-15/door-lasttime/icon-1024.png (the live PWA icon, also served at https://buckthem.com/lasttime/icon-1024.png, 200) (source size 1024x1024)
- `resources/icon.png`: 1024x1024
- `resources/splash.png`: 2732x2732 — icon centered at 1200x1200 on white, built with PIL.

## Toolchain notes

- npm install staged in `/tmp/tf-lasttime` then node_modules/ + package-lock.json copied into the shell (workspace fs refuses chown → EPERM, per recipe).
- `npx cap add ios` and `npx cap sync ios` run in the shell dir; CocoaPods/xcodebuild skips on this Linux VM are expected — no iOS compilation attempted or claimed. Status: READY-FOR-MAC.

## Flags / gaps

None.
