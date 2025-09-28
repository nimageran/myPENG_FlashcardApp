# Nima Flashcards — README

## What this is
This is a simple flashcards webpage. It is one file (`index.html`) that loads your deck from `assets/cards.csv`. It works on your iPhone and your laptop.

## Folder layout
```
repo/
├─ index.html
└─ assets/
   ├─ cards.csv
   └─ images/
      └─ (put images here)
```

## CSV format
Your CSV has three columns: `id,front,back`.
The app converts every id to `card<number>`. For example, `21` or `Card021` becomes `card21`.

Example:
```
id,front,back
21,What is torque?,τ = r × F
Card003,PID stands for?,Proportional–Integral–Derivative
```

## Images
If the normalized id is `card21`, name the image `card21.png` (or `.jpg/.jpeg/.webp/.svg`). Put it in `assets/images/`.
Images show only on the back of the card.

## Editing later
To add a card, append a new row and give it a new number (for example `22`). Optionally upload `assets/images/card22.png`.
To delete a card, remove its row. You may also delete the matching image file. Other cards will not break.
To change wording, edit only `front` or `back`. Do not change the id number.
You can reorder rows. Images will stay correct because they follow the id, not the row.

## If an image does not show
Check that the filename matches the id exactly, including lowercase. Make sure the file is inside `assets/images/`. Refresh the page after you upload.

