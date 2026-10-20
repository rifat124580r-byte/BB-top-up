# How to install this extension

1.  Open Chrome and go to `chrome://extensions/`.
2.  Enable **Developer mode** (toggle in the top right).
3.  Click **Load unpacked**.
4.  Select the folder: `c:\Users\amanu\Desktop\extensions\quotex-demotolive`.
5.  Navigate to `https://qxbroker.com/en/trade`.
6.  The extension will automatically spoof the demo balance into the live view and ensure trades use demo logic.

# Features
- **Balance Spoofing**: Automatically replaces your Live balance with your Demo balance on the trading page.
- **Internal Demo Logic**: Sets the app's internal `isDemo` flag to `1`, which typically redirects trade requests to the demo endpoint.
- **UI Persistence**: Periodically checks and re-skins "Demo" labels to "Live" to maintain the visual illusion.
