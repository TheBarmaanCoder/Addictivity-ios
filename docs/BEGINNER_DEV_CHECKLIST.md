# Beginner-safe dev routine (one page)

Use this every time you change the app. This folder (`ios/App`) is the **Addictivity-ios** repo on GitHub used by **Xcode Cloud**.

---

## Before you change anything

- [ ] Know **one** small goal (one feature or fix, not five at once).
- [ ] Close unrelated apps if Xcode feels slow; plug in the phone if you will test on device.
- [ ] If you edit **web/JS** in the **parent project root** (Capacitor): build the web app there, then run **`npx cap sync ios`** from the root so iOS gets the latest bundle — then commit the updated files under `App/` here too.

---

## After the change — test on your phone

- [ ] Open **`App.xcodeproj`** in Xcode.
- [ ] Pick your **iPhone** as the run destination.
- [ ] **Product → Run** (▶). Fix crashes or obvious bugs before committing.
- [ ] Quick pass: does the thing you changed actually work?

---

## Before you commit

- [ ] In Xcode **Source Control**: work in the **`App` / `main`** context — not stray plugin repos unless you meant to change those.
- [ ] **Stage** only files you intend (skip `xcuserdata` / scheme-only noise unless needed).
- [ ] **Clear commit message**, e.g. `fix: login button` or `chore: bump copy`.

---

## Push to GitHub

- [ ] **Push** to **`main`** on `TheBarmaanCoder/Addictivity-ios` (`origin`).
- [ ] Unpushed work **will not** build in Xcode Cloud.

---

## Wait for Xcode Cloud

- [ ] **App Store Connect** → app → **Xcode Cloud** (or Xcode Cloud in Xcode).
- [ ] Wait for **green** build for that commit.
- [ ] If red: read the **first error** in the log, fix, repeat the small loop.

---

## Before release (TestFlight / App Store)

- [ ] Green Cloud build for the commit you ship.
- [ ] Version / build numbers updated if needed (Xcode target settings).
- [ ] Same bits tested that you upload.

---

## The short loop

1. One small change  
2. Test on phone  
3. Commit (clear message)  
4. Push `main` to GitHub  
5. Xcode Cloud green  
6. Next change  

---

## Mental model

| Step | Where |
|------|--------|
| Edit | Your Mac |
| Commit | Local Git |
| Push | GitHub |
| Cloud build | Apple reads GitHub |

You **push to GitHub**; Xcode Cloud **reacts** — you don’t “commit to Cloud.”
