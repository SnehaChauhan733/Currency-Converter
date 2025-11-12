# Currency Converter

A lightweight, responsive web application to convert amounts between currencies using real-time exchange rates and visual country flags.

## Key Features
- Convert any supported currency to another using live exchange rates.
- Country flags shown for selected currencies (based on a currency-to-country mapping).
- Primary and fallback APIs for reliable rate retrieval.
- Mobile-friendly, minimal UI suitable for embedding or learning purposes.

## Tech Stack
- Plain HTML, CSS and vanilla JavaScript
- APIs:
  - Primary: https://api.exchangerate.host
  - Fallback: https://open.er-api.com
- Flag source: https://flagsapi.com (driven by mappings in codes.js)

## Project Structure
- index.html — Application markup and assets.
- style.css — Styling and responsive behavior.
- codes.js — Currency-to-country ISO mappings for flags.
- script.js — App logic: populate selects, update flags, fetch and display rates.
- README.md — This document.

## Getting Started (Local)
1. Clone or download the project folder.
2. Serve the directory to avoid possible CORS issues (recommended):
   - Python 3: `python -m http.server 8000`
   - Node (http-server): `npx http-server -p 8000`
3. Open `http://localhost:8000` in your browser and use the app.

You can also open `index.html` directly in a browser for quick testing, but using a local server is recommended.

## Usage
1. Enter an amount (default is 1).
2. Select the source ("From") and target ("To") currencies.
3. Click "Get Exchange Rate" to fetch and display the converted amount and rate.

Example output: "1 USD = 82.50 INR"

## API Notes & Failure Handling
- The app queries exchangerate.host first; if that fails, it falls back to open.er-api.com.
- If an API response is missing a rate for the requested currency pair, the UI will display an error and further details will appear in the browser console (DevTools).
- Rate values are formatted to two decimal places.

## Troubleshooting
- "Error fetching exchange rate" — open DevTools (F12) and inspect the console for the failing request and response.
- Missing flags — verify `codes.js` contains a mapping for the currency code. The flags use country ISO codes to render images from flagsapi.com.
- Network/CORS issues — run the app through a local static server rather than opening the file directly.

## Contributing
- Bug reports, documentation improvements, and small patches are welcome.
- Please open an issue first for significant changes or new features.

## License
MIT

## Contact
For questions or help running the project, open an issue in the repository or contact the maintainer listed in the project metadata.
