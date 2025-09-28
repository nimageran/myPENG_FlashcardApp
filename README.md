# Nima Flashcards — README

This guide focuses on two things:
1) **What the app/code does** (so you know how to use it).
2) **How to handle images + edit the CSV safely** (so nothing gets messed up).

---

## 1) What the app does (in plain words)
- **Single‑file web app** (`index.html`) that runs on your iPhone and laptop.
- **Auto‑loads your deck** from `assets/cards.csv` at page open.
- **Front/back flashcard flow**: question on front, answer on back.
- **Images only on the back**: so the question isn’t spoiled.
- **Two play modes**: **Random** or **Ordered**; optional **Skip Known**.
- **Local progress**: marks Known/Unknown and counts Seen (saved per device in localStorage).
- **Text‑to‑speech (TTS)**: reads the card when you flip/advance (tap **Start** once on iPhone to unlock audio).
- **Responsive UI**: big touch areas, works on mobile and desktop (clamp‑based sizing).
- **ID normalization**: any CSV `id` is normalized to **`card<number>`** (e.g., `21` → `card21`, `Card003` → `card3`).
- **Image mapping by ID**: looks for `assets/images/card<number>.(png|jpg|jpeg|webp|svg)`.

**Minimal repo**
```
repo/
├─ index.html
└─ assets/
   ├─ cards.csv
   └─ images/
      ├─ card1.png
      ├─ card2.jpg
      └─ ...
```

---

## 2) CSV + images — the rules to avoid mistakes

### CSV format
- **Columns (required):** `id,front,back`
- **ID can be loose** in the file (e.g., `21`, `Card003`, `card12`). The app will **normalize** at runtime to `card<number>`.
- **Front**: your question/prompt
- **Back**: your answer/explanation

**Example `assets/cards.csv`**
```
id,front,back
21,What is torque?,τ = r × F
Card003,PID stands for?,Proportional–Integral–Derivative
card12,Duty of care?,Engineers must act with reasonable care and skill
```
At runtime these become IDs: `card21`, `card3`, `card12`.

### Image mapping (back side only)
- Put images in `assets/images/` with filenames that **match the normalized ID**:
  - `card21.png`, `card3.jpg`, `card12.webp`, …
- Supported extensions: `.png`, `.jpg`/`.jpeg`, `.webp`, `.svg`.
- If a card has **no image**, simply don’t upload one.

**Why normalization helps**
- You don’t need to remember the exact formatting you typed in CSV; just remember the **number**.
- Whatever you wrote (`21`, `Card003`, `card12`), the app expects the **image name** using `card<number>`.

**How to find the right number**
- In the CSV, check the `id` value and grab its digits (e.g., `Card003` → **3**).
- In the app UI, the label shows the **normalized ID** (e.g., `card3`), so you can name the file **exactly** like that.

---

## 3) Safe editing workflow for 2 months of study

### Adding a new card
1. Append a new row at the end of `cards.csv`.
2. Give it an `id` that contains the next **number** (e.g., `22`, `Card022`, or `card22`).
3. (Optional) Upload its image as `assets/images/card22.png` (or .jpg/.webp/.svg).

> Tip: The number must be **unique**; don’t reuse old numbers.

### Deleting a card
- Remove its row from `cards.csv`.
- (Optional) Delete the corresponding image file (e.g., `card7.png`). Leaving it is harmless.

### Editing wording
- Change only `front`/`back`. Leave the `id` number as‑is to keep the image link.

### Reordering rows
- Fine. IDs keep images glued; order doesn’t matter.

---

## 4) Common mistakes (and how to avoid them)
- **Using filename from position** (e.g., the 22nd card shown today):
  - Don’t use deck position. Use the **ID number**. If your CSV `id` is `Card003`, name your image `card3.png`.
- **Mismatched case or spacing**:
  - Keep filenames lowercase, no spaces: `card21.png` (not `Card 21.PNG`).
- **Wrong extension**:
  - If you uploaded `.jpg` but expect `.png`, it won’t load. Keep the extension consistent.
- **Cache confusion on GitHub Pages**:
  - Wait ~30–60 seconds after pushing; then hard‑refresh (iPhone Safari: reload; Desktop: Cmd+Shift+R / Ctrl+F5).

---

## 5) Quick checklists

**Before studying**
- [ ] `assets/cards.csv` has `id,front,back`
- [ ] New IDs have unique numbers
- [ ] Images named `assets/images/card<number>.<ext>`
- [ ] Page updated on GitHub Pages and hard‑refreshed
- [ ] Tap **Start** once on iPhone to enable audio

**When an image doesn’t show**
- [ ] Does a file exist at `assets/images/card<number>.<ext>`?
- [ ] Does the filename exactly match the **normalized ID** (case‑sensitive)?
- [ ] Is the extension correct? Try `.png` if unsure.
- [ ] Hard‑refresh after upload.

---

## 6) Example end‑to‑end
1. Add to CSV: `Card045,Conflict of interest?,Disclose and manage conflicts to protect the public`
2. Upload image: `assets/images/card45.png`
3. Open site → Go to this card → Flip → you’ll see answer + `card45.png`.

That’s it — simple, stable, and hard to mess up.

