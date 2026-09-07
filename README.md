# Tax Invoice Desk

A single-page invoice generator for Australian sole traders and small businesses.
Save your business, ABN and bank details once, then build each invoice from a saved client and a saved service.

## What it does

- **Details saved once.** Business name, ABN, phone, email, address, logo and the full bank block (bank, account name, BSB, account no, PayID) are entered once and reused on every invoice.
- **Numbers itself.** Invoice numbers come from a prefix plus a counter, which moves up on its own once you download or save an invoice.
- **Saved clients.** Pick a client from the dropdown and all five bill-to fields fill in.
- **Saved services.** Press the star on a line item to keep it, then drop the whole row back in from the service picker.
- **Recent invoices.** Duplicate any past invoice with a fresh date and number.
- **Live preview.** The A4 page updates as you type. Download as PDF or print.

A repeat invoice is three actions: pick a client, pick a service, download.

## Where the data lives

Everything is stored in the browser's `localStorage` and never leaves the machine.
There is no server and no account.

Use **Back up to file** in *My details* to export a JSON copy of your details, clients, services and recent invoices, and **Restore** to load it on another device or after clearing site data.

## Running it

There is no build step. `index.html` is the whole application.

Open the file directly in a browser, or serve the folder:

```
python3 -m http.server 8000
```

Two resources load from a CDN: Google Fonts, and `html2pdf.js` for the PDF export.
Everything else, including all state, is local. If the PDF library cannot load, the download falls back to the browser print dialog, where "Save as PDF" produces the same page.
