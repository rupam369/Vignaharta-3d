# 🙏 VIGHNAHARTA — The Lost Modak (3D)

> “Every journey has a purpose. Every obstacle has a way through.”

A complete, playable **Ganesh Chaturthi festival adventure game in real-time 3D**,
built for the **NIAT / SGSU Ganesh Chaturthi Game Design Contest** (Batch 2026).

You play **Mushak**, Lord Ganesha's mouse companion — a fully procedural low-poly
3D character with idle / walk / jump / celebrate animations — on a journey through
**5 explorable 3D festival worlds** to recover the Lost Modak before the Utsav ends.

## 🎮 The 5 Worlds (Three.js / WebGL)

| # | World | Gameplay |
|---|-------|----------|
| 1 | 🏮 Festival Streets | Explore the moonlit bazaar, find 3 brass fragments, light festival diyas, dodge rolling carts, climb the flag-steps |
| 2 | 🌸 Rangoli Courtyard | Memory-pattern — walk to the glowing flames and light them in order to bloom the rangoli |
| 3 | 🌧️ Monsoon Ghat | Rain-slick platforming — leap stones & boats, ring the ghat bell, light 8 floating diyas |
| 4 | 🛕 Temple Courtyard | Replay the diya melodies, spin each chakra until its gold petal meets the flame, ring the temple bell |
| 5 | 🎆 Grand Finale | 6 offerings → 3 flames in order → diya-mandap lock → walk-to-mandap cinematic: **THE MODAK HAS RETURNED · GANAPATI BAPPA MORYA** |

Plus: **📅 Daily Challenge** (seeded per date — “Collect N Modaks in 90 seconds”),
**8 achievements**, stars, combos (x1–x5), checkpoints, persistent saves,
generative music + full procedural SFX.

### Controls

- **Desktop:** WASD / arrows to move · mouse-drag to look · Space jump · E interact
- **Mobile:** left virtual joystick · drag right side to look · JUMP + gold USE buttons · tap glowing objects directly

## 🛠️ Tech (100% original code, zero external assets)

- **Next.js 14 + React 18 + TypeScript + Three.js** (WebGL directly — no fake 3D)
- Third-person follow camera (drag-look, auto-align, shake, smoothing), pooled
  particles, instanced diyas/bunting, capped lights, zero React re-renders in the loop
- **Web Audio API** — 6 generative music modes + 3 ambience beds + 30+ synthesized
  SFX with pitch-variation, combo tiers, collision cooldowns; master/music/sfx volumes
- **localStorage** — progress, stars, bests, settings, volumes, daily bests
- All art is **procedural low-poly geometry in code** (Mushak, diyas, rangoli, ghat,
  temple, marigold, fireworks, rain, petals) — no copyrighted assets, no model files
- No backend, no API keys, no paid services

## 📁 Code Map

```
app/                    Next.js shell (layout, page router, global CSS)
src/components/
  Screens.tsx           Title · Story intro · World map
  GameView3D.tsx        WebGL host · HUD · joystick · touch buttons · pause/results
  Overlays.tsx          Pause · Results · Settings (+volumes) · How-to · Achievements
src/game/
  types.ts  storage.ts  audio.ts  engine.ts  daily.ts   (HUD/result/save/audio core)
src/game3d/
  core.ts  camera3d.ts  player.ts  mushak.ts  art.ts
  particles3d.ts  floaters.ts  input3d.ts  levelbase.ts
  levels/  level1.ts … level5.ts
```

## ▶️ Run Locally

```bash
npm install
npm run dev     # → http://localhost:3000
npm run build   # production check (must pass before submitting)
npm start
```

## 🚀 Deploy to Production (Vercel — free, ~5 minutes)

**Prerequisites:** Node.js ≥ 18.17, a GitHub account, a Vercel account.
No environment variables, no API keys, no backend, no database.

**1 · Push to GitHub**

```bash
cd vighnaharta
git init
git add .
git commit -m "Vighnaharta 3D — production release"
git branch -M main
git remote add origin https://github.com/<you>/vighnaharta.git
git push -u origin main
```

**2 · Deploy on Vercel**

1. https://vercel.com → **Add New… → Project** → Import the repo
2. Framework is auto-detected as **Next.js** — keep the defaults:
   - Build command: `npm run build`
   - Output directory: (Next.js default)
   - Install command: `npm install`
   - Environment variables: **none needed**
3. Click **Deploy** → you get `https://<game>.vercel.app` → that's the public **game link**

**3 · Every player plays independently**

- Progress (unlocked worlds, stars, bests, settings) is stored in each player's
  own browser `localStorage` (`vighnaharta-save-v1`) — no accounts, no server,
  one user can never affect another.
- Fully responsive: desktop (WASD + mouse), tablet and mobile (joystick + touch).
- All art is procedural code and all audio is synthesized Web Audio — zero
  external asset files, nothing to upload or host separately.

**4 · Updates:** push to `main` → Vercel auto-redeploys in ~1 minute.

## 🎬 Demo Video Tips (for the submission form)

- Record 60–90 seconds: Title → Story → World 1 3D exploration + fragment → diya
  lighting → World 3 rain glimpse → Finale cinematic (“THE MODAK HAS RETURNED”)
- Use free OBS / phone screen-record; upload unlisted to YouTube or Drive
- Show mobile joystick + USE button for 10 seconds (judges love mobile-ready games)

## 🔧 Playtest shortcut

On the World Map, press **U three times** to unlock all 5 worlds instantly
(local browser only, for testing — judges will never stumble on it).
To relock, use Settings → Reset all progress.

## 📝 Submission Checklist

- [ ] Game link (Vercel URL)
- [ ] Source code (GitHub repo link or ZIP of this folder)
- [ ] Demo video link
- [ ] Short description: “Vighnaharta — The Lost Modak: a 5-world 3D Ganesh Utsav
      adventure starring Mushak. Explore night-festival worlds, solve diya &
      rangoli puzzles, master the monsoon ghat, and bring the Lost Modak home —
      with daily challenges, achievements and full mobile support.”

**Ganapati Bappa Morya! 🙏**
