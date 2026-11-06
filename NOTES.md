# Tutor Site — Working Notes

## Status
- Part (A) Practice page: **working** (standalone index.html)
- Part (B) Rehearsal mode: **planned, not built**
- Part (C) Resources page: **planned, not built**
- GitHub Pages: **live and working** (repo is public — required for Pages on free plan)

## Live URLs
- Student link (in use by student, via WeChat): https://engzone.ct.ws/cet/4/001
- GitHub mirror (working): https://shamrockds.github.io/engzone/
- GitHub exercise: https://shamrockds.github.io/engzone/exercises/cet/4/001/
- Repository: https://github.com/shamrockds/engzone

## Repository structure (current, on master branch)
engzone/
├── index.html                     ← teacher landing page (existing, 3 weeks old)
└── exercises/
    ├── .gitkeep
    ├── songs.html                 ← moved from root
    ├── songs/
    │   └── somewhere-out-there.html  ← moved from root
    └── cet/
        └── 4/
            └── 001/               ← first exercise (this chat's build)
                ├── index.html     ← practice page (MP3 + recorder + progress tracker)
                ├── model_A.mp3
                ├── model_B.mp3
                └── model_C.mp3

## Files in local project folder
- index.html — CET-4 style practice page (MP3 playback, take-list recorder,
  CSV/ZIP progress export, email button, all fallbacks)
- model_A.mp3, model_B.mp3, model_C.mp3 — model readings for passages A/B/C
- NOTES.md — this file (handoff memory card)
- (no exercise.json or engine.js yet — the current index.html is still the
  standalone version; the JSON-driven refactor is planned, not built)

## Architecture decisions (already agreed)
- One template, two modes: `practice` and `rehearsal` (flag in JSON)
- JSON-driven exercises (exercise.json) — engine.js reads it
- Shared style.css and engine.js for all pages
- Folder structure: /exercises/, /students/, /assets/, /teacher/
- Exercise tree: exercises/<exam>/<level>/<number>/ (e.g. cet/4/001/, hkdse/listening/,
  sat/, listening/songs/)
- Student pages = one folder per student, plain links
- Model audio: MP3 in same folder as HTML (primary), speech synthesis (fallback)
- Recording: take list (multiple takes, per-take Play/Save/Delete)
- Progress: localStorage + CSV export + ZIP export + optional email
- No backend, no login. Static site (GitHub Pages).
- Student work is NOT stored in the repo — student downloads CSV/ZIP and sends
  via email/WeChat/Telegram. Cloudflare R2 considered for later, not needed now.
- Repo must be public for GitHub Pages on the free plan.

## Planned folder structure (not yet built)
- exercises/ (exists) → cet/, hkdse/, sat/, listening/ (only cet/ exists so far)
- students/<name>/index.html — one dashboard per student
- resources/index.html + resources.json — searchable library (Part C)

## Next steps
1. Update NOTES.md with live URLs after each milestone (done — this file)
2. When ready: build students/ folder (one dashboard per student)
3. When ready: build resources/ (Part C, JSON-driven, searchable, filterable)
4. Then Part (B): rehearsal mode (timer, pause, withhold feedback)
5. (Later) Refactor the standalone index.html into the JSON-driven
   template + engine.js — only after Part (B) is working.

## Environment
- GitHub repo is public (required for Pages on free plan)
- Student's live link is still InfinityFree (untouched); GitHub is a mirror
- Teacher email in index.html: shamrockds@gmail.com

## Lessons learned (GitHub interface)
- When editing a file, always choose "Commit directly to the master branch"
  (a branch mix-up once made a moved file "disappear" from the main view).
- The trash-can icon in the file view has moved into the "…" (three-dot) menu.
- 404 after upload usually means Pages not yet propagated (1–3 min) or Pages
  not enabled on master / (root).
