# Vanguard: Shadow Ops (static project)

No build step. Serve this folder over http(s); opening index.html from disk will not load the GLB files.

    npx vercel --prod        # or: npx serve .

## Assets and credits
- `assets/tex/*`: original tileable PBR texture sets (colour, normal, roughness for ground, wall, metal, wood), generated procedurally for this project. No third-party art, so no licence to track.
- `assets/ui/key-art.jpg`, `assets/ui/hero.jpg`: Rydetech key art and the hero portrait cropped from it. Confirm you hold the rights to this art before publishing to a platform.
- `assets/models/soldier.glb`: the "Soldier" character from the three.js examples (Mixamo rig and animations: Idle, Walk, Run).
  Mixamo characters and animations are free to use in projects, including commercial ones, but may not be redistributed or sold as standalone assets.
- `vendor/*.js`: three.js r128 and its post-processing/loader scripts (MIT), bundled locally. No CDN or third-party requests at runtime.
- `vendor/fonts`: Anton and Barlow (SIL Open Font License), bundled locally.
- Weapon models: optional, see `assets/weapons/README.md`.

If a model fails to load, the game falls back to its built-in procedural characters and guns.

## Phones and tablets
Touch controls turn on automatically on phones and iPads (Settings has Auto, Always on, Off). Landscape is required.
On iPhone or iPad use Share, then Add to Home Screen for a full-screen app. All music is generated in the browser. The game makes no external network requests.

## CrazyGames readiness
- Original assets only (procedural characters, vehicles, textures; the third-party soldier GLB is disabled via `USE_GLB = false`).
- SDK v3 wired (`Gameplay start/stop`, `Loading start/stop`, `happytime`, midgame ad at natural break, Data module for best score, mute-audio setting). Every call is a no-op off-platform.
- On the platform (or with `?cg=1`) the title card is skipped: one click on Play lands in gameplay.
- No custom fullscreen button, no external links, no cross-promotion, English only, PEGI 12 style (non-gory impacts).
- Initial download about 6 MB, 60 files, relative paths only.
- HUD verified legible at 800x450 (DPR 1) and on phone landscape; physics are delta-time based (frame-rate independent).
