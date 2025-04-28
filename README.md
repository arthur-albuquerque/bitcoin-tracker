# Bitcoin Tracker

## Overview

Bitcoin Tracker is a web-based application designed to help users monitor their Bitcoin (BTC) investments in Brazilian Real (BRL). It allows users to track purchases, taxes, and transfers of Bitcoin (in satoshis), providing a summary of total satoshis held, total BRL spent, average purchase price, current value, and profit/loss based on live market prices. The tool also supports monthly average price tracking and data backup/import functionality for persistence.

This project was developed by Arthur Albuquerque, with assistance from **Grok**, an AI created by xAI. Grok provided guidance, debugging support, and code improvements to ensure accurate calculations, especially for complex scenarios like transfers and zero-BRL purchases.

## Features

- **Add Transactions**:
  - Record Bitcoin purchases (satoshis and BRL cost).
  - Log taxes paid in satoshis.
  - Track transfers (sell or move satoshis) using market price or manual input.
- **Summary**:
  - Total Satoshis: Current satoshi balance.
  - Total BRL Spent: Net BRL spent after transfers.
  - Average Price: Weighted average price per BTC (in BRL), adjusted for transfers and zero-BRL purchases.
  - Live Price: Fetched from Cointrader Monitor API ([https://cointradermonitor.com/preco-bitcoin-brasil](https://cointradermonitor.com/preco-bitcoin-brasil)).
  - Current Value: Value of holdings based on live price.
  - Profit/Loss: Percentage gain/loss based on average price vs. live price.
- **Transaction History**:
  - View and delete past transactions.
- **Monthly Average Prices**:
  - Records the live BTC price on the 1st of each month.
- **Data Persistence**:
  - Export transactions and monthly prices to a JSON file.
  - Import data to restore previous state.
- **Responsive Design**:
  - Built with Tailwind CSS for a clean, mobile-friendly UI.

## Tech Stack

- **HTML/CSS/JavaScript**: Core web technologies for the frontend.
- **Tailwind CSS**: For styling and responsive design.
- **Cointrader Monitor API**: Fetches live BTC/BRL prices.
- **LocalStorage**: Stores transaction data locally in the browser.
- **GitHub Pages**: Hosts the application.

## Usage

1. **Access the App**:
   - Visit [https://arthur-albque.github.io/bitcoin-tracker/](https://arthur-albque.github.io/bitcoin-tracker/) on any modern browser (tested on Safari and Chrome).
   
2. **Add Transactions**:
   - Select a date and transaction type (Purchase, Tax, or Transfer).
   - For **Purchases**: Enter satoshis and BRL amount (e.g., 147,960 sats for 800 BRL).
   - For **Taxes**: Enter satoshis paid (e.g., 200 sats).
   - For **Transfers**:
     - Choose **Market Price** (requires live price) or **Manual Input**.
     - Market: Enter BRL to transfer (e.g., 700 BRL → 130,353 sats at 537,000 BRL/BTC).
     - Manual: Specify satoshis and BRL (e.g., 130,353 sats, 700 BRL).
   - Click **Add Transaction**.

3. **View Summary**:
   - See your total satoshis, BRL spent, average price, current value, and profit/loss.
   - Live price updates every 60 seconds or manually via **Retry Live Price**.

4. **Manage Transactions**:
   - View history and delete transactions as needed.

5. **Track Monthly Prices**:
   - On the 1st of each month, the live price is recorded in the Monthly Average Prices table.

6. **Backup and Restore**:
   - Click **Export Data** to download `bitcoin-tracker-backup.json`.
   - Use **Import Data** to upload a previous backup and restore your data.

## Example

- **Purchase**: Bought 147,960 sats for 800 BRL on 2025-04-26.
- **Tax**: Paid 200 sats on 2025-04-26.
- **Transfer**: Transferred 130,353 sats (700 BRL at market price) on 2025-04-27.
- **Summary** (Live Price: 537,000 BRL/BTC):
  - Total Satoshis: 17,407
  - Total BRL Spent: 100.00
  - Average Price: ~540,686 BRL/BTC
  - Current Value: ~93.47 BRL
  - Profit/Loss: ~0%

## Development and Collaboration

This tool was created by **Arthur Albuquerque** as a personal project to manage Bitcoin investments. I collaborated with **Grok**, an AI assistant developed by xAI, to enhance the application. Grok helped with:

- Debugging calculation errors (e.g., average price issues after transfers).
- Handling edge cases, such as purchases with 0 BRL cost.
- Optimizing JavaScript code for accuracy and performance.
- Providing detailed testing steps and validation logic.

Grok’s assistance was instrumental in ensuring the tool accurately tracks cost basis, handles market and manual transfers, and maintains data integrity through backup/import features.

## Installation (For Development)

1. Clone the repository:
   ```bash
   git clone https://github.com/arthur-albuquerque/bitcoin-tracker.git
   ```
2. Open `index.html` in a web browser to run locally.
3. To deploy on GitHub Pages:
   - Push changes to the `main` branch.
   - Ensure GitHub Pages is enabled in the repository settings (source: `main` branch).

## Known Limitations

- **Live Price Dependency**: Requires an internet connection to fetch live prices from Cointrader Monitor.
- **Zero BRL Purchases**: Affects average price calculations (warning added during input).
- **Browser Storage**: Data is stored in `localStorage`, which may be cleared if browser data is wiped. Use Export/Import to back up data.


## License

This project is licensed under the MIT License. 

## Contact

For questions or feedback, reach out to Arthur Albuquerque via GitHub: [arthur-albuquerque](https://github.com/arthur-albuquerque).
