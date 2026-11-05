# Udyam Digital prototype

A no-build, browser-based prototype for the Project Udyam Digital journey. It reads the provided synthetic catalogue, GSTIN/Udyam registries and lead data directly from `../YTL_TrackA_Udyam_Digital_Data/`.

## Run it

From the workspace root, start a local static server:

```sh
python3 -m http.server 8000
```

Open [http://localhost:8000/prototype/](http://localhost:8000/prototype/). The browser must be able to reach the sibling data folder; opening `index.html` as a `file://` URL will not load the CSV files.

## Demo path

1. Answer the five business questions and generate the rules-based shortlist.
2. Choose a bundle, toggle optional products, then continue to verification.
3. Give consent before entering registry lookups or loading KYC specimens. Try a valid active GSTIN from the mock registry, or pick specimen **K01** to show a cancelled GSTIN and **K11** to show stale address proof.
4. Use any specimen that includes both signatory ID and address proof to place a demo order, then open Order tracker.
5. Open Partner desk to browse synthetic leads.

## Prototype boundaries

- Bundle eligibility, catalogue starting prices, minimum terms and per-site quantities are computed from the supplied catalogue. Product eligibility is checked before showing a recommendation.
- Registry checks use the supplied CSVs in the browser. KYC extraction, e-sign, payment, partner notification, address-level network feasibility and installation updates are simulations; there is no external API or GenAI call.
- Documents are not uploaded or retained by a server. Selected specimen files are read by filename and local availability; the local files remain in the provided data folder. The demo order is stored in browser `localStorage`.
- Partner desk scores are illustrative placeholders, not the model/AUC described in the business-case PDF.
- The interface can be switched between English and Hindi with the language control in the top bar. Business names and some catalogue-specific names remain as supplied in the source data.
