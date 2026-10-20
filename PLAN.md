# Implementation Plan - Quotex Demo-to-Live Extension

This extension will modify the behavior of the Quotex trading platform on the live trading page (`/trade`) to display the demo balance and execute trades using demo logic.

## 1. Project Structure
- `manifest.json`: Extension configuration.
- `content.js`: Main content script to inject the spoofer.
- `inject.js`: Injected script that runs in the page context to modify `window.settings`.

## 2. Core Logic
### A. Interception
- The extension will detect if the URL is `https://qxbroker.com/*/trade`.
- It will inject `inject.js` as a "main world" script (available in MV3).

### B. Spoofing `window.settings`
Inside the main world:
- Wait for `window.settings` to be available.
- Force `isDemo: 1`.
- Overwrite `liveBalance` with the value of `demoBalance`.
- This trickery should make the frontend React app believe it is in demo mode even while on the live URL.

### C. UI Consistency
- We will add a mutation observer or interval to check if the balance display elements need a manual override if the app updates them from a different source.

## 3. Verification Plan
1. Load extension in Developer Mode.
2. Navigate to `https://qxbroker.com/en/trade`.
3. Observe if the balance changes to the Demo value.
4. Attempt a trade.
