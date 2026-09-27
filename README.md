# KEY-HORSE / THE FRONT DOOR

**[Open the browser flasher](https://0ct0s3c.github.io/m5khorse-flasher/)**

A pocket library. A few radios. A horse with no business supervising a fucking
thing. Now available through a browser, because apparently the door needed to
be easier to open.

This repository carries the built browser installer and compiled firmware for
**M5Stack PaperMono C153 with NFC + LoRa**. Firmware source is maintained
separately. My luggage is public. My unfinished manuscripts are not.

## Consult the deeply unqualified

The page deals all 78 Horse Tarot cards with upright and reversed readings.
Draw one card or choose **Past / Present / Future** for three distinct cards.
Select a position to read it, reverse the card, or use **Previous** and **Next**
to revisit the last twelve readings during this page visit. The cards have
opinions. They have no access to the fucking USB port.

Black, white and neutral gray. One Tarot illustration at a time. The separate
librarian portrait has left the page; his language remains a public nuisance.

## A bigger library. A longer alibi.

The [latest field notes](https://0ct0s3c.github.io/m5khorse-flasher/#whats-new)
cover all **72 commits from `563ef7d` through `451429f`**, grouped by what changed:

- EPUB/FB2 reading and local PDF/DjVu book import.
- File Commander and USB transfer recovery.
- NOGPS maps, walking-aware surveys and more careful estimates.
- Wi-Fi/LoRa spectrum inspection.
- Named keepsakes, hidden stories and bond chapters.
- Settings, frontlight and sound controls.
- On-device clock setup, saved-Wi-Fi NTP and alarms.
- Flashless e-paper cleanup and explicit recovery.
- Shared text, NFC, voice, message and memory fixes.

Three highlights lead into nine expandable chapters in the existing monochrome
page. [Read or download the full changelog](changelog.md) for capabilities,
limits and complete commit coverage, including the reverted change.
The dated notes cover firmware `451429f`; the installer always reports the
actual checked package. No USB connection is needed to read the notes or Tarot.

## Let the bastard in

1. Open the flasher in **desktop Chrome or Edge**.
2. Connect your **PaperMono C153** with a USB data cable. Close serial monitors
   and other flashers first.
3. Confirm the board on the page. Hold the power/reset button about two seconds
   and release when the LED blinks to enter download mode.
4. Choose **Connect PaperMono**, then **Install KEY-HORSE**.
5. Wait for verification, then check the display, touch and NFC on the device.

No Python, compiler, account or local server is needed to use the hosted page.
Bring the right board and a data cable. The attitude is already bundled.
PaperMono-Lite, Paper and PaperS3 are different devices; family resemblance is
not an installation instruction.

## The horse kept the receipts

The page checks the manifest and every firmware download with **SHA-256**,
requires **ESP32-S3 / 16 MB flash**, and verifies each written segment against
the device's **MD5 digest**. Chip detection cannot identify the exact board:
check PaperMono C153 yourself.

The four-segment installation preserves existing KEY-HORSE settings, horse
progress and device PIN, and never accesses the microSD card. It avoids a
whole-chip erase and never automatically retries an interrupted installation.
Verified bytes and a working screen are separate pieces of evidence. I have
been asked to stop treating confidence as a diagnostic instrument.

Open **Release files & installation log** on the page to download the manifest,
individual segments or the log of your session. The manifest records the actual
compiled revision, exact offsets, lengths and hashes.

| Segment | Flash offset |
| --- | --- |
| `bootloader.bin` | `0x0` |
| `partitions.bin` | `0x8000` |
| `boot_app0.bin` | `0xe000` |
| `K-HORSE-papermono.bin` | `0x10000` |

The current package is **`451429f`**. Its embedded revision, image headers,
partition boundaries and all four SHA-256 digests were checked before
publication. Display appearance, touch, NFC and radio behavior still need a
hands-on check. The paperwork is in order. My bedside manner remains appalling.

Bundled browser dependency notices are in [licenses.txt](licenses.txt) and
[app.js.LEGAL.txt](app.js.LEGAL.txt).

## Keep the stable in one piece

This is a static GitHub Pages repository. Publish `main` from the repository
root; `.nojekyll` keeps the generated files intact. Each firmware package has a
directory named for its manifest's SHA-256. Add the complete verified package
before updating `release.json`, and preserve manifest bytes exactly.

The browser receives only the published site and firmware files. It never
needs access to the firmware source repository.

[Fund the oat dependency](https://buymeacoffee.com/0ct0). HR has blocked our number.
