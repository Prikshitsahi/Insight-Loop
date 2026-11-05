# InsightLoop — Vercel-ready website

InsightLoop is a static, browser-based customer and business intelligence prototype. It lets a visitor upload one or more CSV or Excel files, combine the rows, map columns, refresh dashboard summaries, inspect common issues, and export an action plan.

## What's included

- `index.html` — the complete website. No build step is required.
- `northstar_retail_customer_experience_2000.csv` — 2,000-row synthetic sample dataset.
- `northstar_retail_customer_experience_2000.xlsx` — the same sample data in a workbook, with summary and data dictionary sheets.
- `vercel.json` — static hosting headers and clean URL settings.

The first page load starts with the 2,000-row Northstar Retail demonstration dataset. The sample data is fictional and must not be represented as real customer research or actual retailer performance.

## Deploy using Vercel's website (easiest)

1. Extract this ZIP file on your computer.
2. Create a new GitHub repository and upload the **contents** of the extracted `insightloop-vercel` folder (make sure `index.html` is at the repository root).
3. Sign in to Vercel and choose **Add New → Project**.
4. Import the GitHub repository.
5. Select **Other** as the framework preset. Leave the Build Command and Install Command empty. Set the Output Directory to `.` if Vercel asks for one.
6. Select **Deploy**. Vercel will provide a public website URL.

## Deploy using the Vercel CLI

Install the Vercel CLI if it is not already installed, then run these commands from this folder:

```bash
npm install -g vercel
vercel
```

Follow the prompts. To publish the production deployment, run:

```bash
vercel --prod
```

## Using the website

- **Add Dataset** appends the rows from selected CSV/XLS/XLSX files to the current dataset.
- **Replace Current Data** replaces the in-memory dataset with the selected files.
- **Restore 2,000-row demo** restores the included synthetic sample data.
- The theme switch in the header toggles light and dark appearance.
- The mapping tab lets you choose which source columns represent satisfaction, recommendation score, issue category, comments, segment, date and return outcome.
- The export controls download the combined data and the current rule-based action plan.

The CSV parser is built into the page. Excel file reading uses the SheetJS browser library from jsDelivr (`cdn.jsdelivr.net`), so users need an internet connection when opening Excel files. If that CDN is blocked, CSV uploads will still work.

## Important product limitations

- This is a static front-end website. It has no database, login, backend API or shared multi-user storage.
- Uploaded records are processed in the visitor's browser and are held in memory only. They are not saved to Vercel and are cleared when the page is reloaded or closed.
- The current recommendations are transparent, keyword/rule-based suggestions—not generative AI. They should be validated before operational use.
- All included Northstar data is synthetic demonstration data.

For a production product with saved datasets, user accounts, shared workspaces or an AI model, add a secure backend/database and authentication, plus a server-side API with appropriate privacy and access controls.
