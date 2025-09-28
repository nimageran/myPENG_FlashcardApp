# Nima NPPE Flashcards — README

This is a short guide for **using the flashcards app** and **keeping images mapped to the right cards** (even after editing the CSV).

---

## 1) What’s in the repo
```
repo/
├─ index.html              # the app (auto‑loads CSV, light theme, audio, mobile‑friendly)
└─ assets/
   ├─ cards.csv            # your deck (id,front,back)
   └─ images/              # (optional) card images live here
      ├─ card1.png
      ├─ card2.jpg
      └─ ...
```

---

## 2) The CSV format (required)
- **Columns**: `id,front,back`
- **ID**: a stable string like `card1`, `card2`, `card3`. **Never change an existing ID.**
- **Front**: the question/prompt
- **Back**: the answer/explanation

**Example**
```
id,front,back
card1,What is torque?,τ = r × F
card2,PID stands for?,Proportional–Integral–Derivative
card3,Duty of care?,Engineers must act with reasonable care and skill
```

> You can add an optional third column later (e.g., `img`) if you want, but this setup doesn’t require it.

---

## 3) How the app works (quick use)
1. Open your GitHub Pages site (e.g., `https://<user>.github.io/<repo>/`).  
   The app **auto‑loads** `assets/cards.csv`.
2. Tap **Start** (unlocks audio on iPhone).
3. **Tap card** to flip. Use **I don’t know / I know / Next** or keyboard:  
   Space = flip, → = next, `1` = unknown, `2` = known.
4. **Modes**: switch **Random / Ordered**; **Skip Known** to focus on what you don’t know.
5. Progress (Known/Unknown/Seen) saves locally (per device). Use **Reset** to clear.

---

## 4) Images — the rule that keeps things clean
**You chose the ID‑matching rule.** If an image exists for a card, name the image file **exactly** the same as the card ID and place it in `assets/images/`.

- ID → `card7`  → image file → `assets/images/card7.png` (or `.jpg`/`.jpeg`/`.webp`/`.svg`)
- If a card has **no image**, just omit the file.

**Result:** editing the CSV (reorder rows, delete some, add new ones) won’t break images because each image is tied to a **stable ID**, not the row number.

### Optional (multiple images)
If you ever need more than one image for a card, use suffixes:
```
assets/images/card7-1.png
assets/images/card7-2.png
```
(Your app can default to the first; rotating is an optional future tweak.)

---

## 5) Uploading images (GitHub web UI)
**Goal:** Add an image for `card12`.
1. Go to your repo → `assets/images/` → **Add file** → **Upload files**.
2. Upload a file named **`card12.png`** (or `.jpg`, `.webp`, etc.).
3. Commit the change. That’s it — the app will show it for `card12`.

> If you already have an image with a different name, rename it in GitHub to match the ID (e.g., from `torque.png` to `card12.png`).

---

## 6) Editing the CSV later (safe workflow)
- **Add a new card**: append a new row at the end with a **new ID** (e.g., `card21`). If needed, upload `assets/images/card21.png`.
- **Delete a card**: remove its row. Optionally delete its matching image. Existing IDs in other rows **do not change**.
- **Change wording**: edit `front`/`back` only. **Do not change `id`**.

**DO**
- Keep IDs lowercase and simple (no spaces) → `card1`, `card2`, `card3`.
- Consider zero‑padding if you like neat sorting (`card001`, `card002`) — optional.

**DON’T**
- Don’t rename IDs after creation. (That would orphan the image.)
- Don’t rely on row numbers for image mapping.

---

## 7) GitHub Pages tips
- After editing CSV or uploading an image, Pages can take **30–60 seconds** to update.
- If you don’t see changes, do a **hard refresh**:
  - iPhone Safari: tap URL bar → pull down to reload, or toggle Airplane mode briefly.
  - Desktop: `Cmd+Shift+R` (Mac) or `Ctrl+F5` (Win).

---

## 8) Troubleshooting images
- **Card shows no image**: check that `assets/images/<id>.<ext>` exists and the **filename matches the ID exactly** (case‑sensitive), and that the extension is correct.
- **Wrong image**: confirm the CSV `id` for that card and the image filename match. If you duplicated a row and forgot to change the ID, fix the duplicate.
- **Still old image**: hard‑refresh (see above) or add a small query string like `?v=2` to the image once (future enhancement) to break cache.

---

## 9) Example checklist before study
- [ ] CSV saved as UTF‑8, columns `id,front,back`
- [ ] New rows appended with **new IDs**
- [ ] Images named `assets/images/<id>.<ext>`
- [ ] GitHub Pages updated (wait ~1 min), then hard refresh
- [ ] Audio unlocked by pressing **Start** on iPhone

---

## 10) Optional enhancements you can add later
- A `decks/` folder (e.g., `assets/decks/ethics.csv`, `law.csv`) with a dropdown.
- A `card audio` button to replay TTS on demand.
- Dark‑mode toggle (for night study).