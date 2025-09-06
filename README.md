# Aaradhya's Kitchen — Static Website (Zero-cost)

This repository contains a single-file static website (`index.html`) for **Aaradhya's Kitchen**.
It loads the menu from a **Google Sheet (published to web)** and supports WhatsApp ordering, UPI QR, and a printable menu.

## What’s included
- `index.html` — main website (mobile-first, Google Sheets integration)
- `assets/Aaradhyas_Kitchen.jpg` — your logo
- `sample_menu.csv` — example Google Sheet CSV data to copy into your sheet

## How to use (Google Sheets as menu source)
1. Open the provided `sample_menu.csv` in the repo (or use the demo sheet link provided separately).
2. Create a new Google Sheet, then copy the rows from `sample_menu.csv` (first row must be headers: `Name,Price,Description`).
3. In Google Sheets: **File → Share → Publish to web**. Choose the sheet and format **Comma-separated values (CSV)** and publish.
4. Copy the published sheet's **Sheet ID** from the URL. Example URL:
   `https://docs.google.com/spreadsheets/d/<SHEET_ID>/edit#gid=0`
5. Open `index.html` and replace the placeholder `REPLACE_WITH_SHEET_ID` (near the top of the file) with your `<SHEET_ID>`.
6. Deploy the repo:
   - **GitHub Pages**: push to a public repo and enable Pages (choose `main` branch / root). Site will be available at `https://<username>.github.io/<repo>/`.
   - **Netlify**: drag & drop the repo or `index.html` into Netlify Drop.
   - **Vercel**: import repo or drag & drop.

## WhatsApp ordering
Each menu item has an **Order via WhatsApp** button. Clicking it opens WhatsApp with a pre-filled message:
```
Hello Aaradhya's Kitchen,
I'd like to order: [Dish Name]
Quantity: [please specify]
Delivery Address: [please specify]
Payment Mode: UPI / Cash on Delivery
```
WhatsApp number used: `+91 89281 34960`.

## UPI Payment
- UPI ID prefilled: `nsg06041987@okicici`
- QR code is generated dynamically (uses Google Chart API). Customers can scan in their UPI app.

## Notes & troubleshooting
- If the menu doesn't load after you set `SHEET_ID`, ensure your sheet is published to web as CSV. The site fetches:
  `https://docs.google.com/spreadsheets/d/<SHEET_ID>/gviz/tq?tqx=out:csv`
- Test Mode (toggle in the sidebar) allows you to preview local sample menu without using Sheets.

## Replacing the logo
Replace `assets/Aaradhyas_Kitchen.jpg` with your preferred logo image (same filename) if needed.

---

If you'd like, I can also:
- Create a real Google Sheet for you and publish it (requires Google account access — not done here).
- Push this repo to GitHub for you (I can give instructions or provide git commands).
