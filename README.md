# Ethiopia Governance Visualizations

Interactive static HTML visualizations of Ethiopia's governance structure:

- `index.html` (combined entry page for all visualizations)
- `ethiopia_government_flowchart.html`
- `ethiopia_government_network.html`
- `ethiopian_government_structure.html`

## Run Locally

1. Open this folder in a terminal.
2. Start a local static server:

```powershell
python -m http.server 8000
```

3. Open:

- `http://localhost:8000/`
- `http://localhost:8000/ethiopia_government_flowchart.html`
- `http://localhost:8000/ethiopia_government_network.html`
- `http://localhost:8000/ethiopian_government_structure.html`

You can also open the files directly in a browser, but a local server is recommended.

## Share Online (GitHub Pages)

1. Push this repo to GitHub.
2. In GitHub: `Settings -> Pages`.
3. Source: `Deploy from a branch`.
4. Branch: `main`, folder: `/ (root)`.
5. Open the generated Pages URL.

## Security Notes (Audit Summary)

- Added a restrictive CSP meta policy and `referrer` policy to all pages.
- Reduced DOM injection risk by escaping dynamic text before inserting HTML in the network view.
- Replaced one `innerHTML` breadcrumb sink with `textContent` in the structure view.

Remaining considerations:

- External dependencies (D3, Google Fonts) are loaded from CDNs; this is a supply-chain and privacy consideration.
- Data is currently static and embedded in files; if you later load user input or remote JSON, keep escaping/sanitization in place.
