# Tutor Site — Working Notes

## Status
- Part (A) Practice page: **working** (index.html in this folder)
- Parts (B) Rehearsal and (C) Resources: **planned, not built**
- GitHub Pages: **next task**

## Files in this folder
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
- Student pages = one folder per student, plain links
- Model audio: MP3 in same folder as HTML (primary), speech synthesis (fallback)
- Recording: take list (multiple takes, per-take Play/Save/Delete)
- Progress: localStorage + CSV export + ZIP export + optional email
- No backend, no login. Static site (GitHub Pages).

## Next steps
1. GitHub step 1: create repository, upload files, enable Pages
2. Then Part (B): rehearsal mode (timer, pause, withhold feedback)
3. Then Part (C): resources page (JSON-driven, searchable, filterable)
4. (Later) Refactor the standalone index.html into the JSON-driven
   template + engine.js — only after Part (B) is working.

## Environment
- Currently experimenting on InfinityFree
- GitHub account exists, Pages not yet set up
- Teacher email in index.html: shamrockds@gmail.com