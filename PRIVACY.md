# Privacy Policy

_Last updated: 2026-06-08_

**Car QR Contact** is a free, open-source, fully client-side tool. This policy
explains — honestly — what happens to your data, and the limits of what
"private" means here.

## The short version

- There is **no server and no database** behind this tool. It is a single static
  HTML page.
- Nothing you type into the form is **stored, transmitted, logged, or shared** by
  us. We could not see your phone number even if we wanted to.
- Your phone number, plate, and message are encoded **inside the QR code / link
  itself**, and live only in the QR image you download and on the device of
  whoever scans it.

## How it works (data flow)

1. You open the page and fill in your number, plate, and message.
2. Everything is processed **in your browser**. A QR code is generated locally.
3. The contact details are packed into the part of the URL **after the `#`**
   (the "hash fragment").
4. When someone scans your QR, their browser loads the page and reads that hash
   fragment **on their own device** to display your masked number and a call
   button.

By web standard, **the part of a URL after `#` is never sent to the web
server.** So even the host that serves this page (GitHub Pages) does not
receive your phone number — its logs only ever see that "the page was loaded,"
not the contact data.

## Important limitation: "masked" is not "encrypted"

The masking (e.g. `+1 ***-***-1234`) only controls **what is displayed on the
screen**. Your **full** phone number is embedded inside the QR code and the link
so that the "Call Owner" button can actually dial you.

This means **anyone who obtains your QR image or your link can technically
decode the full number** — the data is encoded (base64), not secret or
encrypted. Treat your QR like a business card: only display or share it where
you are comfortable with people being able to reach you.

## Third-party services

To keep the tool simple, the page loads two resources from third parties when it
opens. **Neither receives your phone number or any form data** — they only serve
static assets:

- **Cloudflare CDN (cdnjs)** — serves the QR-code generation library.
- **Google Fonts** — serves the display fonts. Google may log the visitor's IP
  address as part of serving fonts, per Google's own policies.

If you self-host this tool and want **zero external requests**, you can inline
the QR library and remove the web fonts — the project is open source and you are
free to modify it.

## Hosting

This page is published via **GitHub Pages**. Like any web host, GitHub may keep
standard server access logs (IP address, timestamp, requested path). These logs
**do not contain** the contact data, because that lives only in the URL hash
fragment, which is never sent to the server. See GitHub's privacy statement for
details on their logging.

## No tracking

This tool uses **no analytics, no cookies, no accounts, and no third-party
trackers**.

## Your responsibility

You decide what number and message to encode and where to display the resulting
QR code. Please only share contact details you are comfortable making reachable.

## Contact

Questions about this policy or the project can be raised as an issue on the
[GitHub repository](https://github.com/erayon/car-qr-contact).
