# KEY-HORSE changelog

Changes are grouped by what you can do with the horse. Each entry describes the
final behavior at its **Through** revision; earlier implementation steps are not
separate features.

## 451429f — 27 September 2026

**Since:** `563ef7d` (the web flasher's previous firmware, published 22 September).
**Through:** `451429f`. **Scope:** all 72 intervening commits, 22–27 September 2026.

A bigger library. A longer alibi. The horse has learned to open more books,
keep a few things that matter and make slightly better sense of where he is.
He has also acquired a clock-setting page. Punctuality remains a character flaw
he is unwilling to develop.

### Reading and book formats

- Open **EPUB and FB2** directly from `/books`, alongside existing UTF-8 TXT
  books. Chapter/body text reflows at the selected text size and reading progress
  is saved. EPUB/FB2 are text-only: publisher layout and illustrations are omitted.
- **File commander → Import book** converts **PDF and DjVu** locally in the
  browser to `.khbook`. Preview a page, choose ink strength and a page range,
  then upload. The converters ship on the device and need no Internet service;
  originals remain intact. PDF and DjVu are not opened directly by the reader.
- Converted books preserve page images and diagrams, with full-page navigation,
  four 2× detail views and page bookmarks. They do not reflow or earn word-based
  reading rewards. Associated voice notes keep the document page.
- Preserve text around embedded bodies and block elements; handle stress marks,
  `№`, SVG cover pages and oversized markup more reliably. Skip hidden library
  files and avoid unnecessary display servicing while parsing FB2.
- Distinguish damaged books, SD read errors, oversized metadata and unsupported
  DRM in English and Polish. Broken encryption metadata is an error, not proof
  of DRM. Failed opens keep the previous book, and failed bookmark saves retain
  the current page and shortcut return for another try.

### File Commander and transfers

- Import dialogs now show their own upload progress, start with a valid page
  range and close when a browser session expires so sign-in is reachable again.
  The local Commander preview also serves the bundled conversion assets.
- Wi-Fi drafts, selected networks, keyboard layout and saved-network list pages
  survive Settings and shortcut detours. Returning does not restart the server.
- Check **every page** of the destination folder before a batch upload starts.
  Duplicate names, cancelled checks and incomplete listings send no files.
  Existing files are not overwritten. Recoverable `.part` files are visible;
  internal transfer staging files remain protected.
- USB WiGLE region/map replacements keep the old file until the replacement
  arrives completely and passes readback. USB replies flush their final packet,
  upload tools accept larger status replies, and transfers tolerate longer
  device stalls. Book/WiGLE chunk acknowledgements wait for the progress frame
  to finish; a display fault or timeout cancels the unfinished upload.

### NOGPS maps, estimates and walking

- Keep pins and map scale through transient SD failures, distinguish a failed
  read from a missing file, and reload a replaced region index. A larger map,
  north arrow, on-map estimate radius and shorter captions leave more room for
  the location itself.
- Save the region anchor, follow recent pins or estimates, read ahead at tile
  edges and search outward within a time budget. Bound wider searches so unknown
  addresses do not repeatedly send the device through the whole city index.
- Count steps and turns from the BMI270 FIFO during NOGPS surveys. While walking,
  survey every **20 seconds** instead of every minute. Improve slow-turn
  detection and retain a walk log for inspection.
- Use fresh observations from the current survey, expire unsupported estimates,
  treat sibling BSSIDs as one radio, reject radio outliers and fit reference
  power instead of assuming one transmitter strength. Guard the near-distance
  model against falsely narrow uncertainty rings.
- Add fit journals and host replay, cached-map address/street/district lookup
  for choosing an anchor, and resumable regional WiGLE collection tools.
- **NOGPS remains a Wi-Fi-based estimate**, requiring matching region data and
  an offline map on microSD. It is not GPS or demonstrated pedestrian navigation.
  Synthetic uncertainty coverage is not measured outdoor accuracy.

### Wi-Fi and LoRa spectrum views

- Use consistent peak markers, plot scales, reference ticks, cursors and history
  rows on both analyzers. Wi-Fi gains **LATEST / HOLD** and tap-to-inspect levels;
  completed live previews say **FINAL**.
- LoRa gains **FULL / ×4 / ×16** spans around the saved mesh frequency, four RSSI
  reads per bin and a median level. Retained captures keep their original window.
- Keep Wi-Fi textures on one running average. HT40 CSI mapping is covered on the
  host, but the device still listens at HT20; this is not live 40 MHz capture.
  Wi-Fi envelopes remain modeled AP footprints, not measured spectral power.

### MY HORSE, keepsakes and stories

- Give all **10 mementos** named keepsake scenes. Add **7 hidden-history stories**
  and **4 bond chapters** at the existing 0 / 100 / 300 / 1,000 XP thresholds.
  Existing valid saves reveal already-earned scenes without a reward reset.
- Distinguish **Kept**, **Awaiting save** and unavailable progress. New scenes
  open after checked persistence; previously kept stories stay readable during
  later save failures. **Retry save** does not spend food.
- Show progress toward the selected milestone and stop story navigation at the
  ends. Recover saved-melody and pomodoro achievements after a restart, and avoid
  counting a continued word as another newly read page.
- Let alarm remarks through the horse's quiet period and choose comments that
  fit the actual event. No new XP thresholds, offline penalties or streak guilt.

### Settings, frontlight and sound

- Organize Settings into **Display, Sounds, Buttons, Sleep, Clock, Alarms & timers,
  LoRa and Device lock**. Display and shortcut choices have focused pages; the
  index shows current preferences and returns to the covered task.
- Lower the frontlight drive for **Dim / Soft / Room** to approximately
  **0.4% / 3.5% / 25% PWM duty**. These are electrical levels, not measured brightness.
- Add independently saved **Off / Quiet / Soft / Clear** levels for UI and
  notification cues, plus six previews. Improve cue drive and completion
  diagnostics. Muted previews stay inactive; page turns and text entry stay quiet.
  Recordings and alarms retain their own volume behavior.
- Read back saved preferences and offer **Retry save**, including on Sleep.
  Closing Settings clears discarded editors and stale shortcut returns; retained
  drafts keep their place. Physical buttons keep the action shown during a refresh.

### Clock and alarms

- Set the local date/time on the device, or use **Sync now** with File commander's
  saved Wi-Fi networks. Try another profile when connection or NTP fails, and
  release Wi-Fi after completion or confirmed cancellation.
- Add saved automatic NTP and timezone choices: **Warsaw / EU daylight saving**,
  UTC, or fixed offsets. Zone conversion applies on synchronization; an offline
  clock needs a later sync or manual correction after a zone/DST change.
- Confirm RTC writes by reading them back, recover oscillator validity after a
  verified write, and preserve timer/pomodoro deadlines when correcting the clock.
- Use consistent date/time/alarm keypads, clear stale validation notices, and
  allow physical A or B to silence a ringing alarm at the PIN screen.

### E-paper refresh and recovery

- Carry the last successfully displayed image through partial refreshes, add
  flashless OTP correction and reinforce persistent top/bottom ink in both palettes.
- The **final behavior in 451429f** is two passes per submitted frame: its first
  update, followed by exactly **one whole-frame cleanup pass showing the same
  image**. The first pass retains its eight-partial correction cadence. There is
  no scheduled third pass or idle repaint. Earlier single-pass notes are history.
- Wait for both passes and confirmed controller sleep before advancing image
  history, allowing device sleep or acknowledging upload progress. Startup and
  refresh faults retain explicit recovery and power-off status instead of retrying
  indefinitely. A fresh touch/button action can explicitly retry panel startup.
- Ship M5Stack and FreeInk display-driver notices with browser and firmware
  packages. The extra waveform costs time and energy; physical ghosting, visible
  flashing and panel appearance still need inspection on the actual device.

### Everyday reliability

- Fit wrapped text, accented glyphs, editor carets, NFC notes and message bubbles
  by their visible ink. Improve Shift/Backspace behavior, header refreshes and
  centered status notices across screens.
- Let handled recording failures and settled message/LoRa drafts stop blocking
  sleep. Start playback without an unnecessary list refresh and clear stale
  book-page context before the next recording.
- Restore NFC use after a confirmed RF-off retry and return a stopped copy to
  its saved source. Keep saved captures distinct from fresh unsaved reads.
  Incomplete Type 2 archives retain their missing-page map; copies skip unread
  pages and unsupported presentation/content sharing stays unavailable.
- Move the BLUES workspace into PSRAM and release unused M5GFX canvas memory
  for radio startup. Add scratch-buffer guards, heap checks and retained fault
  evidence; remove unused host-tool imports. These changes do not establish
  physical RF, touch, sound or outdoor-location acceptance.

### Commit coverage

Every commit in `563ef7d..451429f` appears once below, under its principal area.
Cross-cutting fixes are also described in the relevant functional sections above.

| Area | Commits |
| --- | --- |
| Reading | `05e6b61` `bc8cf12` `bc05f89` `673be90` `cadff8a` |
| Commander and transfers | `ddd9997` `fb24909` `3250bcb` `225fc6e` `c8ec26d` `9db2bd1` `d32f1ad` `cf5ec30` |
| NOGPS and walking | `fe6f65c` `6cece33` `19aa4cd` `d1c85cd` `a61690e` `9368854` `1b62892` `f0efeb3` `5889d68` `db664a1` `8c74896` `69512ea` `2b1b93b` `9d6a26e` `0644d39` `a0c16ff` `e06991f` `121e433` `e6ae76c` `51d99f3` `9c75573` `f2ae91a` `b389380` |
| Spectrum | `12db48c` `5cc7e0c` |
| Horse progression and voice | `bf05be0` `9448789` `290d15c` `1bb7aaa` `7c65c0d` `9da2e02` `59fc368` |
| Settings and sound | `fe5f6d3` `6836d8c` `27172af` `9e7f498` `5a1c7cc` `006272b` `6870403` `f55c091` |
| Clock and alarms | `f797542` `81c91d9` `dd908a1` `2d1bdae` `2444f47` |
| E-paper | `bba174e` `e593a98` `a4c041a` `80f4b28` `29b88e7` `451429f` |
| Shared UI, memory and recovery | `32a7faf` `8fb1550` `9af7758` `ec9643e` `c8e63d4` `09cc5c6` `0c5d9a1` `1ba344e` |

`9da2e02` reverts `7c65c0d`; their cancelled behavior is not advertised as a
delivered feature. The separate kept-scene heading change in `1bb7aaa` remains.

### Updating

Use the PaperMono C153 web flasher's four-segment update. It preserves existing
KEY-HORSE settings, horse progress and PIN, and does not access microSD files.
EPUB/FB2 go in `/books`; PDF/DjVu need File commander's Import book first.
NOGPS needs your own matching region/map data on microSD.

Firmware hashes identify installed bytes. Display, touch, RF and audible output
remain checks on your device. The horse's confidence is still not a test instrument.
