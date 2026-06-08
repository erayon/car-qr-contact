# 🚗 Car QR Contact

A free, **server-less** tool to generate a privacy-friendly QR sticker for your
car. Someone scans it, sees a **masked** phone number and your message, and taps
**Call Owner** to reach you — your full number never appears on the page.

**Live tool:** https://erayon.github.io/car-qr-contact/

## Why

Generic QR generators just encode your full number as a `tel:` link, exposing it
to anyone. Parking apps need a backend. This fills the gap: a **car-specific
contact page** with a **masked number** and a **custom message**, that needs
**no server, no account, and no database**.

## How it works

- One static HTML file does both jobs:
  - Open it plain → the **generator** (fill in number, plate, message).
  - Open it with contact data in the URL hash → the **contact page** scanners see.
- The QR encodes a normal URL like
  `https://erayon.github.io/car-qr-contact/#<encoded-data>`.
- The contact data lives in the URL **hash fragment**, which browsers never send
  to the server — so nothing is logged or stored anywhere.

## Usage

1. Open the [live tool](https://erayon.github.io/car-qr-contact/).
2. Enter your phone number, plate (optional), and a message.
3. Click **Generate**, then **Test Page** to preview what scanners will see.
4. **Download PNG**, print it (a laminated card works well), and place it on your
   dashboard or windshield.

## Self-hosting

It's a single file. Drop `index.html` on any static host (GitHub Pages, Netlify,
Vercel, Cloudflare Pages). No build step, no backend.

## Privacy

There is no server and nothing is saved. **Important:** "masked" means hidden
from view, **not encrypted** — the full number is embedded in the QR so the call
can connect, and anyone with your QR image can decode it. Share it accordingly.
See [PRIVACY.md](PRIVACY.md) for the full policy.

## License

[MIT](LICENSE) © 2026 erayon
