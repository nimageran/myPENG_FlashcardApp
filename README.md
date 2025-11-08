# Nima Flashcards — README
**Note:** Edit the Excel file inside the Excel folder, as it is not possible to make some changes, like highlighting, in CSV. After editing the Excel, save it as CSV and replace the CSV file inside the asset folder.
## How this works (big picture, in two simple paragraphs)
This is a single-page web app (`index.html`) you open on your iPhone or laptop. When the page loads, it automatically reads your deck from `assets/cards.csv`. Each row becomes one flashcard with a **front** (question) and a **back** (answer). You flip by tapping the card, and it uses a quick rotate animation so it feels like a real card. If you swipe right, it marks “I know.” If you swipe left, it marks “I don’t know.” Your known/seen progress is saved locally on each device.

Cards use stable IDs. Whatever you put in the CSV `id` column gets normalized to `card<number>` (for example `21`, `Card021`, and `card21` all become `card21`). Images are optional and only show on the back. The app looks for a file named after that normalized ID inside `assets/images/`, so the link between a card and its image stays correct even if you rearrange rows.

## How to edit the CSV later (remove rows, add rows, change text)
Your CSV must have exactly three columns in this order: `id,front,back`.
To **remove a card**, delete its entire row from `assets/cards.csv`. That’s it. The rest of the deck keeps working because images and progress are matched by the ID, not by row position. If you want, you can also delete the removed card’s image file from `assets/images/` (for example `card7.png`), but leaving it there does not break anything.

To **add a card**, append a new row at the end and give it a new number in the `id` (for example `22` or `Card022`, which becomes `card22`). Fill in `front` and `back` normally. To **change wording** on an existing card, edit only the `front` and/or `back` text and **do not change the ID number**; this keeps the image mapping and your progress intact. You can reorder rows whenever you want because the app uses the ID, not the position.

## How to add images (now and in the future)
If a card’s normalized ID is `card21`, name the image `card21` with one of these extensions: `.png`, `.jpg`, `.jpeg`, `.webp`, or `.svg`. Put the file in `assets/images/` so the full path looks like `assets/images/card21.png` (or `.jpg`, etc.). The app shows this image on the **back** when you flip the card. Keep filenames lowercase with no spaces to avoid loading issues, and match the ID exactly.

In the future, when you add new cards, follow the same pattern: choose a unique number for the `id`, and drop the matching image into `assets/images/` with that number (for example `card45.png`). When you delete a card, you can also remove its image file to keep the folder tidy. If an image does not appear, double-check the filename exactly matches the normalized ID and refresh the page.
