# KEY-HORSE changelog

Here is what you can actually do with me, grouped by occupation. Each entry
describes the final behavior at its **Through** revision. Earlier attempts stay
in the commit list. I will not invoice you for learning the same trick twice.

## dbe6b35 — 29 September 2026

**Since:** `451429f` (the web flasher's previous firmware, published 27 September).
**Through:** `dbe6b35`. **Scope:** all 34 intervening commits, 27–29 September 2026.

More ways to talk. Fewer interruptions. I acquired two more radio protocols and
learned that a hidden screen needn't interrupt the one you are using. Thirty-four
commits. Apparently shutting up takes engineering.

### Three LoRa modes

- **Messages** now offers **Meshtastic, MeshCore and LoRaWAN**. They share one
  SX1262 radio; changing modes waits for the previous owner to stop. There is no
  cross-protocol bridge, gateway mode or automatic boot transmission. Three
  correspondence desks. One horse to disappoint the recipients.
- **MeshCore** adds signed contact discovery, public-key inspection, channel
  chat and encrypted private messages with recipient acknowledgements. Set the
  clock and match the radio profile and channel key with your peers. Compare
  private-contact keys through a trusted route. A protocol acknowledgement does
  not mean somebody read your masterpiece; the default public channel key does
  not authenticate its displayed sender. No phone-app pairing or repeater role.
- **LoRaWAN** is an **EU868 Class A OTAA end device**. Register it with a network,
  enter its credentials in **Settings → LoRa → LoRaWAN**, then review and send
  **1–51-byte hex payloads**. It requires a gateway and network server. Network
  acknowledgements and application downlinks have distinct results; Class A
  receives only in operation-related windows. I cannot turn a field into a
  network by standing in it with sufficient fucking confidence.
- MeshCore peer exchange and LoRaWAN gateway joins/downlinks still need hardware
  acceptance. Additional EU868 channels below the board's advertised 868 MHz
  lower edge remain unqualified. No additional regional plans or certification
  are claimed. The paperwork has resisted my attempt to sign it with a hoof.

### Conversations and radio recovery

- Opening **Meshtastic or MeshCore** starts listening and shows channel/node
  cards. Both have conversation bubbles, unread badges and presence markers;
  identity details sit behind chat information. MeshCore conversations follow
  public keys, including when names match. LoRaWAN opens payload history and
  joins when needed. The inbox has furniture. Please stop sitting on the radio.
- Leaving stops reception by default. **Settings → LoRa → Keep active** retains
  the selected mode; lock, sleep and other exclusive radio work still stop it.
  A kept LoRaWAN job may finish after leaving. Returning preserves drafts without
  resending them. I can remember a sentence without shouting it twice.
- Editors and Clear/Replace/Remove-trust questions stay usable while incoming
  messages update the inbox. Empty lists cannot reopen stale rows, settings
  paging stops at its ends, and draft recipients stay attached. **Stop radio**
  remains available during refresh and after shutdown failures. Exits wait for
  confirmed shutdown; saved delivery results survive a later power-off error.
- Routine Meshtastic telemetry and advertised positions update the model without
  repeatedly repainting a settled reading frame. Node details catch up on their
  minute refresh or the next action. Messages, new nodes, identities and radio
  state changes remain responsive. The sheep may move without issuing a press
  release to your fucking display.

### E-paper and frontlight

- The final driver adapts FreeInk's B/W flashless sequence: **three same-target
  drives on each of the first three paints after startup or lost history**, then
  **two drives per ordinary frame**. Inverted pages use explicit dark-background
  selectors; the top and bottom ribbons use the same rules as the rest. Repeats
  preserve the target and reference selectors. No inverse visible frame or
  periodic idle repaint is added. I clean the page, not its distant relatives.
- Completed drives, power-down and confirmed controller sleep precede image
  history, sleep readiness and upload acknowledgement. Transport failures retain
  explicit recovery. The shared frontlight supply stays on after ordinary
  refreshes, leaving your **30 / 60 / 90-second** timer in charge. The lamp no
  longer clocks out because the ink finished its shift.
- Owner feedback accepted the display adaptation on 29 September and reported
  remaining ghosting on the **Meshtastic screen**. Later refresh and visibility
  fixes have host coverage; their physical effect on that symptom still needs
  checking. The earlier ribbon/backlight fix was accepted on 28 September.
  A passing byte check cannot look at a screen. Neither can this paragraph.

### Touch, decisions and quiet screens

- One touch or A/B press on an already-visible image can wait up to two seconds
  for refresh and controller sleep to finish, then run once. Changed screens,
  navigation, lock, sleep, held contacts and faults cannot replay it against
  stale controls. Stop and alarm Silence remain available during refresh.
  Your first press has stopped falling between the floorboards.
- Short decisions and completion notices share centered boxes, pixel pictograms,
  inverted ink and an offset shadow. **B chooses the left action; A chooses the
  right.** The box and shadow consume touches; cancellation keeps the draft or
  selection. The experimental Help button and per-screen instruction overlays
  are gone. The horse briefly installed a lecture podium. We removed it.
- Screens covered by Settings, PIN or another feature keep their state moving
  without asking the visible screen to redraw. Covered progress notices finish
  quietly; successful preference saves need no extra frame. Visible failures,
  Sleep controls and eligible alarm notifications remain current. My private
  thoughts no longer require the entire rectangle's participation.

### Horse progress and attention

- Unreadable progress shows dashes and recovery controls instead of invented
  hunger, food or mood. Rewards pause; known session totals and already-kept
  stories survive a later save failure. File Commander distinguishes kept
  achievements from those awaiting save. Missing accounts are not a newborn
  horse. Even my accountant understands that.
- **Shared moments** includes the one-time **Voice Keeper** in its six activity
  counts. Repeated recordings earn nothing extra. Reading credit pauses behind
  transfer progress and while NFC shutdown is unconfirmed. Alarm, timer and
  pomodoro remarks take priority over ordinary chatter; unseen achievements wait
  their turn. My monologue can bloody well survive a queue.

### Sound levels

- UI and notification cues get stronger signal amplitudes: **Quiet and Soft
  rise by 1.5×; Clear by 1.25×**, within the existing output peak limit. These are
  signal changes, not measured acoustic loudness. Off stays silent; recording
  playback and alarms keep their volume behavior. Hear the result on your
  device. I have made the bell less timid, not hired an orchestra.

### Files, transfers and shared reliability

- SD library paths and checked writes now share one implementation; persisted
  byte formats and checksum conventions stay compatible. JSON escaping and
  byte/hex codecs are consolidated. WiGLE rejects truncated MAC addresses, and
  MeshCore checks short packet headers and optional fields before reading them.
  The horse has agreed on which end of a number goes first.
- USB upload tools share framing and accept full BLUES status replies. Firmware
  and host builds agree on the C++ standard, and spectrum formatting stays
  bounded. Browser field notes and the downloadable changelog carry the horse's
  voice throughout. I have tidied the filing cabinet and sworn in every drawer.

### Commit coverage

Every commit in `451429f..dbe6b35` appears once below, under its principal area.
Cross-cutting fixes also appear in the relevant prose above. The first two
documentation commits created the previous release's page and revised its voice;
they are included here because they follow its compiled firmware.

| Area | Commits |
| --- | --- |
| Three LoRa modes | `d129444` |
| Conversations and radio recovery | `9021930` `3c1af1c` `997fbd3` `5259861` `8bf38ef` `9434325` `3ce1cf3` |
| E-paper and frontlight | `656acbb` `f13259c` `af9d1ab` `144b634` `055386e` `66e2af7` `5492ca9` `23a02d0` `4a58f49` |
| Touch, decisions and quiet screens | `78518e7` `4ad97fa` `36d167a` `17a4cf9` `3165b28` `dbe6b35` |
| Horse progress and attention | `50ad02f` |
| Sound levels | `4ee9c2f` `5e0f1be` |
| Files, transfers and shared reliability | `e3dae2e` `9b745a5` `f29bee1` `cfae43e` `fa71ed2` `66923df` `f0cf06a` `10069f3` |

The Help-overlay experiment was superseded by event/decision toasts. Intermediate
edge, supply-isolation and independent-drive experiments are superseded by the
final display sequence above. They are history, not additional release features.
The receipts include the detours. My autobiography would have blamed the road.

### Updating

Use the PaperMono C153 web flasher's four-segment update. It preserves existing
KEY-HORSE settings, horse progress and PIN, and does not access microSD files.
Choose and configure one LoRa mode for the peers or network you actually have.
Check display, touch, audible cues and radio behavior on the device; package
hashes establish the installed bytes. My optimism remains inadmissible evidence.

## 451429f — 27 September 2026

**Since:** `563ef7d` (the web flasher's previous firmware, published 22 September).
**Through:** `451429f`. **Scope:** all 72 intervening commits, 22–27 September 2026.

A bigger library. A longer alibi. I can open more books, keep a few things that
matter and make slightly better sense of where I am. I have also acquired a
clock-setting page. Punctuality remains a character flaw I am unwilling to develop.

### Reading and book formats

- Put **EPUB and FB2** in `/books` alongside your UTF-8 TXT books. Chapter/body
  text reflows at your chosen size, and progress is saved. EPUB/FB2 show text
  only; publisher layout and illustrations stay out. The novel gets a bed. Its
  interior decorator can sleep in the car.
- Use **File commander → Import book** for **PDF and DjVu**: conversion to
  `.khbook` happens locally in your browser. Preview a page, choose ink strength
  and a page range, then upload. The converters ship on the device, need no
  Internet service and leave your originals intact. The reader cannot open
  PDF/DjVu directly. Even my library has a front door.
- Converted books keep page images and diagrams, full-page navigation, four 2×
  detail views and page bookmarks. Voice notes remember the document page.
  These pages neither reflow nor earn word-based reading rewards. The word
  counter cannot eat a photograph.
- Chapter parsing keeps text around embedded bodies and block elements, and
  handles stress marks, `№`, SVG covers and oversized markup more reliably.
  Hidden library files stay hidden; FB2 parsing skips needless display servicing.
  Fewer chances for a perfectly good sentence to vanish down a floorboard.
- Damaged books, SD read errors, oversized metadata and unsupported DRM get
  distinct English and Polish errors. Broken encryption metadata is an error,
  not evidence of DRM. Failed opens keep your previous book; failed bookmark
  saves keep the current page and shortcut return ready for another try.
  I am difficult company, but I needn't eat your place in the book.

### File Commander and transfers

- Import dialogs show their own progress, start with a valid page range and
  close when a browser session expires so you can sign in again. Your upload
  no longer stands across the doorway smoking. The local Commander preview
  also serves the bundled conversion assets.
- Wi-Fi drafts, selected networks, keyboard layout and saved-network list pages
  survive Settings and shortcut detours. Coming back does not restart the server.
  You went to adjust a preference, not abandon the bloody expedition.
- Before a batch upload, **every page** of the destination folder is checked.
  Duplicate names, cancelled checks or incomplete listings send no files;
  existing files are not overwritten. Recoverable `.part` files are visible,
  while internal transfer staging files stay protected. I have learned to check
  whether a shelf is occupied before throwing another book at it.
- USB WiGLE region/map replacements keep the old file until the new one arrives
  completely and passes readback. Replies send their final packet, upload tools
  accept larger status replies, and transfers tolerate longer device stalls.
  Book/WiGLE chunk acknowledgements wait for the progress frame to finish;
  display faults or timeouts cancel the unfinished upload. Arrival before applause.

### NOGPS maps, estimates and walking

- Pins and map scale survive transient SD failures. Failed reads are distinguished
  from missing files, and replaced region indexes reload. A larger map, north
  arrow, estimate radius and shorter captions leave room for the location.
  North has been relieved of its duties as my personal opinion.
- The region anchor is saved; searches follow recent pins or estimates, read
  ahead at tile edges and work outward within a time budget. Wider searches
  are bounded. An unknown address needn't make me re-read the entire city
  like a horse who has lost his cigarette in a telephone directory.
- The BMI270 FIFO supplies step and turn counts during NOGPS surveys. Walking
  brings a survey every **20 seconds**, up from once a minute. Slow turns get
  better detection, and a walk log keeps the evidence. The hooves remain decorative.
- Estimates use fresh observations from the current survey, expire when no
  longer supported, group sibling BSSIDs as one radio and reject radio outliers.
  Reference power is fitted rather than assumed; the near-distance model guards
  against falsely narrow uncertainty rings. A router with several names no
  longer gets to introduce itself as a village.
- Fit journals, host replay and cached-map address/street/district lookup help
  inspect results and choose an anchor. Regional WiGLE collection tools can
  resume. The wandering now leaves notes; future me has already complained.
- **NOGPS remains a Wi-Fi-based estimate** and needs matching region data and
  an offline map on microSD. It is not GPS or demonstrated pedestrian navigation;
  synthetic uncertainty coverage does not measure outdoor accuracy. Please stop
  treating the ring as buried treasure. I cannot afford another shovel.

### Wi-Fi and LoRa spectrum views

- Both analyzers use consistent peak markers, scales, reference ticks, cursors
  and history rows. Wi-Fi adds **LATEST / HOLD** and tap-to-inspect levels;
  completed live previews say **FINAL**. Point at the offending spike. Swearing
  vaguely at the whole atmosphere is exhausting.
- LoRa adds **FULL / ×4 / ×16** spans around the saved mesh frequency, four RSSI
  reads per bin and a median level. Retained captures keep their original window.
  The old picture will not pretend it was taken through your new binoculars.
- Wi-Fi textures share one running average. HT40 CSI mapping has host-test
  coverage, but the device still listens at HT20; it does not capture live 40 MHz
  data. Wi-Fi envelopes remain modeled AP footprints, not measured spectral
  power. Fine curves. The laboratory coat stays on its fucking hanger.

### MY HORSE, keepsakes and stories

- All **10 mementos** get named keepsake scenes, alongside **7 hidden-history
  stories** and **4 bond chapters** at the existing 0 / 100 / 300 / 1,000 XP
  thresholds. Valid saves reveal already-earned scenes without resetting rewards.
  I have become sentimental about crockery. Nobody look directly at me.
- **Kept**, **Awaiting save** and unavailable progress tell you where things
  stand. New scenes open after a checked save; kept stories stay readable after
  later save failures. **Retry save** spends no food. Even I won't charge for
  dinner twice because a file fell over.
- The selected milestone shows its progress, and story navigation stops at the
  ends. Saved-melody and pomodoro achievements recover after a restart. A word
  continued across a page no longer counts as another newly read page. Nice try.
- Alarm remarks can break the horse's quiet period, and comments fit the event
  that actually happened. No new XP thresholds, offline penalties or streak
  guilt. Go and have a life. I can brood over a cup without a fucking timesheet.

### Settings, frontlight and sound

- Settings has eight entries: **Display, Sounds, Buttons, Sleep, Clock, Alarms
  & timers, LoRa and Device lock**. Display and shortcut choices have focused
  pages; the index shows current preferences and returns you to the covered task.
  The cupboard has labels. Please contain your astonishment.
- **Dim / Soft / Room** frontlight drive drops to approximately **0.4% / 3.5% /
  25% PWM duty**. Those are electrical levels, not measured brightness. Dim has
  at least read the job description; judge the light on your own panel.
- UI and notification cues get independently saved **Off / Quiet / Soft / Clear**
  levels and six previews, with improved drive and completion diagnostics.
  Muted previews stay inactive; page turns and typing stay quiet. Every comma
  needn't arrive with a brass band. Recordings and alarms keep their own volume
  behavior; actual audibility still needs a listen on the device.
- Saved preferences are read back, with **Retry save** available even on Sleep.
  Closing Settings clears discarded editors and stale shortcut returns;
  retained drafts keep their place. Physical buttons keep the action shown
  during a refresh. Your abandoned edit no longer waits behind the door to
  jump out at you next Tuesday.

### Clock and alarms

- Set local date/time on the device, or use **Sync now** with File commander's
  saved Wi-Fi networks. Failed connections or NTP requests try another profile;
  completion or confirmed cancellation releases Wi-Fi. I can now establish
  precisely how late I intend to be.
- Save automatic NTP and a timezone: **Warsaw / EU daylight saving**, UTC or a
  fixed offset. Zone conversion happens on synchronization. After a zone/DST
  change, an offline clock needs a later sync or manual correction. Parliament
  moving the clocks does not send a small man into your disconnected horse.
- RTC writes are read back before success, oscillator validity can recover after
  a verified write, and timer/pomodoro deadlines survive clock corrections.
  Moving the hands will not extend your tea break. I checked. Bitterly.
- Date/time/alarm keypads behave consistently and clear stale validation notices.
  Physical A or B can silence a ringing alarm at the PIN screen. The rooster
  now accepts either finger as a formal request to shut the hell up.

### E-paper refresh and recovery

- Partial refreshes carry the last successfully displayed image, with flashless
  OTP correction and reinforced persistent top/bottom ink in both palettes.
  The edges have been asked to stop retaining every visitor's silhouette.
- In **451429f**, each submitted frame gets two passes: the first update, then
  exactly **one whole-frame cleanup pass showing the same image**. The first
  pass keeps its eight-partial correction cadence. No scheduled third pass or
  idle repaint; earlier single-pass notes describe superseded behavior. I wipe
  the table twice. I do not spend the evening polishing your elbow.
- Both passes and confirmed controller sleep must finish before image history
  advances, the device sleeps or upload progress is acknowledged. Startup and
  refresh faults keep explicit recovery and power-off status instead of retrying
  forever. A fresh touch/button action can retry panel startup. You get to ask
  for another attempt; the rectangle needn't have a private nervous breakdown.
- M5Stack and FreeInk display-driver notices travel in browser and firmware
  packages. The extra waveform costs time and energy; ghosting, visible flashing
  and panel appearance still need inspection on the device. My cigarette smoke
  is a poor substitute for a display test.

### Everyday reliability

- Wrapped text, accented glyphs, carets, NFC notes and message bubbles fit by
  their visible ink. Shift/Backspace, header refreshes and centered status
  notices behave more consistently. A letter's accent is part of its head;
  we have stopped seating it through the ceiling.
- Handled recording failures and settled message/LoRa drafts stop blocking sleep.
  Playback skips an unnecessary list refresh, and stale book-page context is
  cleared before the next recording. A failed recording no longer needs an
  all-night vigil from the device that failed to record it.
- NFC works again after a confirmed RF-off retry; a stopped copy returns to its
  saved source. Saved captures stay distinct from fresh unsaved reads. Incomplete
  Type 2 archives keep their missing-page map, copies skip unread pages, and
  unsupported presentation/content sharing stays unavailable. I can carry a
  file. I cannot divine the bits it never contained.
- BLUES moves its workspace to PSRAM, and unused M5GFX canvas memory is freed
  for radio startup. Scratch buffers get guards, heaps get checks, faults leave
  evidence, and unused host-tool imports leave the building. Physical RF, touch,
  sound and outdoor location still need device checks. Tidying my skull does
  not certify everything I do with it.

### Commit coverage

Every commit in `563ef7d..451429f` appears once below, under its principal area.
Fixes that cross areas also appear in the relevant sections above. Seventy-two
commits. Yes, I counted the walk of shame back from a bad idea.

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

`9da2e02` reverts `7c65c0d`; that cancelled behavior is not a delivered feature.
The separate kept-scene heading change in `1bb7aaa` remains. The receipts include
the return trip. My memoir would have quietly skipped that bit.

### Updating

Use the PaperMono C153 web flasher's four-segment update. It preserves existing
KEY-HORSE settings, horse progress and PIN, and does not access microSD files.
EPUB/FB2 go in `/books`; PDF/DjVu need File commander's Import book first.
NOGPS needs your own matching region/map data on microSD.

Firmware hashes identify installed bytes. Check display, touch, RF and audible
output on your device. My confidence once led me into a broom cupboard. Use
better instruments.
