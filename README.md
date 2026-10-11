# Digital Wallet

**Apple Wallet clone for iPhone and web. Add any card you want to your digital wallet.**

<p align="center">
  <img src="wallet-og.jpg" alt="Digital Wallet - Apple Wallet clone" width="600">
</p>

A single-file web app that recreates the iOS Wallet experience: card stack, Apple Pay-style payment screen, the three-dot menu animation, Face ID autofill, bottom sheets and more. No frameworks, no build step, no dependencies. Just open `index.html`.

## Features

- Apple Wallet-style interface with iOS-like animations
- Card payment screen with Face ID animation
- Three-dot menu with the liquid "drop" animation
- Bottom sheets: Add to Wallet, Orders, Preauthorized Payments, Notifications, Transactions
- Toggles with iOS 26 Liquid Glass style
- **Custom card photo**: put any image you want on your card (see below)
- Installable on the iPhone Home Screen with the Wallet icon
- Works offline: everything lives in one HTML file

## How to change the card photo (hidden feature)

The photo change is a secret gesture, so it stays hidden until you unlock it.

### Step 1: Unlock

Tap the screen **15 times in a row**, anywhere on the phone.

- Each tap must come **less than 0.7 seconds** after the previous one. If you pause longer, the counter resets to 1.
- On the 15th tap a message appears: *"Troca de foto liberada!"* and your photo picker opens.
- The unlock is saved on your device, so you only do this once.

### Step 2: Pick a photo

Choose any image from your gallery or camera. The app automatically crops it to the card format (353 x 221) and shrinks it so it fits in the browser storage.

### Step 3: Change it again anytime

After unlocking, you have two ways to swap the photo:

| Method | How |
| --- | --- |
| Hold the card | Press and hold the card for about **0.6 seconds** without dragging |
| Repeat the secret | Tap 15 times in a row again |

### Good to know

- The photo is saved in your browser (`localStorage`), so it stays after you close the page.
- It is stored **only on your device**. Nothing is uploaded anywhere.
- Clearing Safari website data, or using private browsing, removes the saved photo and the unlock.
- The photo also appears on the small card thumbnails across the app.

## Add to iPhone Home Screen

1. Open the site in **Safari**
2. Tap **Share**
3. Tap **Add to Home Screen**

The shortcut uses the Wallet icon (`apple-touch-icon.png`) and the name "Carteira". If you created a shortcut before adding the icon, delete it and add it again, because iOS caches the old icon.

## Run locally

```bash
git clone https://github.com/YOUR-USERNAME/digital-wallet.git
cd digital-wallet
open index.html
```

Or serve it with any static server:

```bash
npx serve .
```

## Deploy

Works on any static host. For GitHub Pages: **Settings > Pages > Deploy from a branch > main / root**.

After deploying, change `og:image` and `twitter:image` in `index.html` to the full URL, for example `https://YOUR-USERNAME.github.io/digital-wallet/wallet-og.jpg`, so link previews work everywhere.

## Project structure

```
.
├── index.html            # the whole app (HTML + CSS + JS + fonts)
├── apple-touch-icon.png  # iPhone Home Screen icon (180x180)
├── wallet-og.jpg         # link preview image (1200x630)
└── README.md
```

## Tech

- Vanilla HTML, CSS and JavaScript
- Web Animations API and CSS transitions
- Embedded SF-style font (base64)
- `localStorage` for the card photo and the unlock state

## Disclaimer

This is a fan-made, non-commercial UI clone for learning and personal use. It is not affiliated with, endorsed by, or connected to Apple Inc. Apple, Apple Wallet, Apple Pay and Face ID are trademarks of Apple Inc. It does not store real payment data and cannot make real payments.

## License

MIT
